# Currency Convertor
#include <stdio.h>

// Defining a structure to represent a currency
typedef struct {
    char name[50]; 
    float exchange_rate; 
} Currency;

float convert(float amount, Currency from, Currency to) {
    return amount * (1 / from.exchange_rate) * to.exchange_rate;
}

int main(void) {
    // Defining currencies and their exchange rates relative to INR
    Currency currencies[] = {
        {"Argentine Peso(ARS)", 1.282}, //1 INR = 1.282 ARS
        {"Australian Dollar(AUD)", 0.019},  // 1 INR = 0.019 AUD
        {"Bahraini Dinar(BHD)", 0.005},//1 INR = 0.005 BHD
        {"Bangladeshi Taka(BDT)", 1.170}, //1 INR = 1.170 BDT
        {"Bhutanese Ngultrum(BTN)", 1.000}, //1 INR = 1.000 BTN
        {"Brazilian Real(BRL)", 0.075},  // 1 INR = 0.075 BRL
        {"Brunei Dollar(BND)", 55.47}, //1 INR = 55.47 BND
        {"Cambodian Riel(KHR)", 0.018}, //1 INR = 0.018 KHR
        {"Canadian Dollar(CAD)", 0.017},  // 1 INR = 0.017 CAD
        {"Chilean Peso(CLP)", 1.021}, //1 INR = 1.021 CLP
        {"Chinese Yuan(CNY)", 0.086},  // 1 INR = 0.086 CNY
        {"Colombian Peso(COP)", 5.433}, //1 INR = 5.433 COP
        {"Danish Krona(DKK)", 0.088}, //1 INR = 0.088 DKK
        {"Egyptian Pound(EGP)", 0.223}, //1 INR = 0.223 EGP
        {"Euro(EUR)", 0.011},  // 1 INR = 0.011 EUR
        {"Ghanaian Cedi(GHS)", 0.759}, //1 INR = 0.759 GHS
        {"Hong Kong Dollar(HKD)", 0.104}, //1 INR = 0.104 HKD
        {"Indian Rupees(INR)", 1},  // 1 INR = 1 INR
        {"Indonesian Rupiah(IDR)", 192.307}, //1 INR = 192.307 IDR
        {"Israeli Shekel(ILS)", 0.046}, //1 INR = 0.046 ILS
        {"Japanese Yen(JPY)", 1.798},  // 1 INR = 1.798 JPY
        {"Kazakhstani Tenge(KZT)", 0.184}, //1 INR = 0.184 KZT
        {"Kenyan Shiling(KES)", 2.624}, //1 INR = 2.624 KES
        {"Korean Won(KRW)", 16.057},  // 1 INR = 16.057 KRW
        {"Kuwaiti Dinar(KDR)", 0.004}, //1 INR = 0.004 KDR
        {"Laotian Kip(LAK)", 0.008}, //1 INR = 0.008 LAK
        {"Malaysian Ringgit(MYR)", 0.056}, //1 INR = 0.056 MYR
        {"Maldivian Rufiyaa(MVR)", 4.830}, //1 INR = 4.830 MVR
        {"Mexican Peso(MXN)", 0.271},  // 1 INR = 0.271 MXN
        {"Mongolian Tugrik(MNT)", 0.026}, //1 INR = 0.026 MNT
        {"Myanmar Kyat(MMK)", 22.383}, //1 INR = 22.383 MMK
        {"New Zealand Dollar(NZD)", 0.020},  // 1 INR = 0.020 NZD
        {"Nepalese Rupee(NPR)", 1.591}, //1 INR = 1.591 NPR
        {"Nigerian Naira(NGN)", 4.343}, //1 INR = 4.343 NGN
        {"Norwegian Krone(NOK)", 0.118}, //1 INR = 0.118 NOK
        {"Omani Riyal(OMR)", 0.005}, //1 INR = 0.005 OMR
        {"Pakistani Rupee(PKR)", 2.272}, //1 INR = 2.272 PKR
        {"Philippine Peso(PHP)", 0.631}, //1 INR = 0.631 PHP
        {"Qatari Riyal(QAR)", 0.049}, //1 INR = 0.049 QAR
        {"Russian Ruble(RUB)", 0.980},  // 1 INR = 0.980 RUB
        {"Saudi Riyal(SAR)", 0.050}, //1 INR = 0.050 SAR
        {"Singapore Dollar(SGD)", 0.018}, //1 INR = 0.018 SGD
        {"South African Rand(ZAR)", 0.209}, //1 INR = 0.209 ZAR
        {"Sri Lankan Rupee(LKR)", 2.756}, //1 INR = 2.756 LKR
        {"Swedish Krona(SEK)", 0.116},  // 1 INR = 0.116 SEK
        {"Swiss Franc(CHF)", 0.012},  // 1 INR = 0.012 CHF
        {"Thai Baht(THB)", 0.452}, //1 INR = 0.452 THB
        {"Turkish Lira(TRY)", 0.108},   // 1 INR = 0.108 TRY
        {"US Dollar(USD)", 0.013}, //1 INR = 0.013 USD
        {"UAE Dirham(AED)", 0.049}, //1 INR = 0.049 AED
        {"Vietnamese Dong(VND)", 296.48}, //1 INR = 296.48 VND
    };

    int convert_from, convert_to;
    float amount;

    printf("Currency Converter:\n");

    // Displaying available currencies
    printf("Currencies available for conversion:\n");
    for (int i = 0; i < sizeof(currencies) / sizeof(currencies[0]); i++) {
        printf("%d. %s\n", i + 1, currencies[i].name);
    }

    // Getting user input
    printf("Enter the number of the currency to convert from: ");
    scanf("%d", &convert_from);
    printf("Enter the number of the currency to convert to: ");
    scanf("%d", &convert_to);
    printf("Enter amount: ");
    scanf("%f", &amount);

    // Performing the conversion
    float result = convert(amount, currencies[convert_from - 1], currencies[convert_to - 1]);

    // Displaying the result
    printf("%.3f %s is %.3f %s\n", amount, currencies[convert_from - 1].name, result, currencies[convert_to - 1].name);

}
