# currencyconverter
<!DOCTYPE html>
<html>

<head>
    <title>Converter</title>

    <script>
        document.addEventListener("DOMContentLoaded", function() {

            document.querySelector('form').onsubmit = function() {
                var type = document.querySelector('#type').value;
                var url = `https://api.exchangeratesapi.io/latest?base=${type}`
                fetch(url)
                    .then(response => response.json())
                    .then(data => {
                        const currency = document.querySelector('#vicky').value;
                        const value = document.querySelector('#number').value;
                        const rate = data.rates[currency];
                        document.querySelector('#result').innerHTML = `1 ${type} equal to ${rate} of ${currency}`;
                        document.querySelector('#value').innerHTML = `${value} of ${type} is equal to ${rate * value} of ${currency}`;

                    })
                return false;
            }
        })
    </script>
</head>

<body>

    <form style="border:3px royalblue;width:40%;margin:100px auto;background-color: slategray;padding:100px;color:white">
        <label>base currency:</label>
        <select name="currency" id="type">
                    <option value="INR">INR(INDIAN RUPEE)</option>
                    <option value="AUD">AUD(AUSTRALIAN DOLLAR)</option>
                    <option value="BRL">BRL(BREZILIAN REAL)</option>
                    <option value="BGN">BGN(BALGARIAN LEV)</option>
                    <option value="CAD">CAD(CANADIAN DOLLAR)</option>
                    <option value="CHF">CHF(SWISS FRANC)</option>
                    <option value="CNY">CNY(CHINICE YUAN)</option> 
                    <option value="CZK">CZK(CZECH KORUNA)</option>
                    <option value="DKK">DKK(DANISH KRONE)</option>
                    <option value="EUR">EUR(EURO)</option>
                    <option value="GBP">GBP(GREAT BRITAN POUND)</option>
                    <option value="HKD">HKD(HONG KONG DOLLAR)</option>
                    <option value="HRK">HRK(CROATIAN KUNA)</option>
                    <option value="HUF">HUF(HUNGARIAN FORINT)</option>
                    <option value="ILS">ILS(ISRAELI NEW SHEKEL)</option>
                    <option value="ISK">ISK(ICELANDIC KRONA)</option>
                    <option value="JAR">JAR(SOUTH AFRICAN RAND)</option>
                    <option value="JPY">THB(THAI BAHT)</option>
                    <option value="KRW">KRW(SOUTH KOREAN WON)</option>
                    <option value="MYR">MYR(MALATIAN RINGGIT)</option>
                    <option value="MXN">MXN(MEXICAN PESO)</option>
                    <option value="NOK">NOK(NORWEGIAN CRONE)</option>
                    <option value="NZD">NZD(NEW ZEA LAND DOLLAR)</option>
                    <option value="PHP">PHP(PHILIPPIAN PESPO)</option>
                    <option value="PLN">PLN(POLAND JLOTY)</option>
                    <option value="RUB">RUB(RASSIAN RUBEL)</option>
                    <option value="RON">RON(ROMANIAN LEU)</option>
                    <option value="SEK">IDR(INDONATIAN RUPEE)</option>
                    <option value="SGD">SGD(SINGAPORE DOLLAR)</option>
                    <option value="TRY">TRY(TURKISH LIRA)</option>
                    <option value="USD">USD(UNITED STATES DOLLAR)</option> 
                  </select><br>
        <label>to:</label><br>
        <label>currency type:</label>

        <select name="money" id="vicky">
                    <option value="USD">USD(UNITED STATES DOLLAR)</option>
                        <option value="INR">INR(INDIAN RUPEE)</option>
                        <option value="AUD">AUD(AUSTRALIAN DOLLAR)</option>
                        <option value="BRL">BRL(BREZILIAN REAL)</option>
                        <option value="BGN">BGN(BALGARIAN LEV)</option>
                        <option value="CAD">CAD(CANADIAN DOLLAR)</option>
                        <option value="CHF">CHF(SWISS FRANC)</option>
                        <option value="CNY">CNY(CHINICE YUAN)</option> 
                        <option value="CZK">CZK(CZECH KORUNA)</option>
                        <option value="DKK">DKK(DANISH KRONE)</option>
                        <option value="EUR">EUR(EURO)</option>
                        <option value="GBP">GBP(GREAT BRITAN POUND)</option>
                        <option value="HKD">HKD(HONG KONG DOLLAR)</option>
                        <option value="HRK">HRK(CROATIAN KUNA)</option>
                        <option value="HUF">HUF(HUNGARIAN FORINT)</option>
                        <option value="ILS">ILS(ISRAELI NEW SHEKEL)</option>
                        <option value="ISK">ISK(ICELANDIC KRONA)</option>
                        <option value="JAR">JAR(SOUTH AFRICAN RAND)</option>
                        <option value="JPY">THB(THAI BAHT)</option>
                        <option value="KRW">KRW(SOUTH KOREAN WON)</option>
                        <option value="MYR">MYR(MALATIAN RINGGIT)</option>
                        <option value="MXN">MXN(MEXICAN PESO)</option>
                        <option value="NOK">NOK(NORWEGIAN CRONE)</option>
                        <option value="NZD">NZD(NEW ZEA LAND DOLLAR)</option>
                        <option value="PHP">PHP(PHILIPPIAN PESPO)</option>
                        <option value="PLN">PLN(POLAND JLOTY)</option>
                        <option value="RUB">RUB(RASSIAN RUBEL)</option>
                        <option value="RON">RON(ROMANIAN LEU)</option>
                        <option value="SEK">IDR(INDONATIAN RUPEE)</option>
                        <option value="SGD">SGD(SINGAPORE DOLLAR)</option>
                        <option value="TRY">TRY(TURKISH LIRA)</option>
                        
                      </select><br>
        <label>amount:</label>
        <input type="number" id="number" placeholder="0000000"><br>
        <input type="submit">

        <br><br><br><br><br><br>
        <p id="result" style="color:rgb(206, 248, 20) ;font-size: larger;"></p>
        <p id="value" style="color:rgb(229, 255, 0) ;font-size: larger;"></p>
    </form>

</body>

</html>
