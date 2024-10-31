# Olio-ohjelmoinnin esimerkkitehtäviä

## Esim1

Demosin Gitin käyttöä

## Esim2

Esimerkkejä funktioista ja header-/cpp-tiedostojen käytöstä

## Esim3

Kertoman ja binomikertoimen laskeminen. 

## try_catch_esim

Sovelluksessa on factorial-metodi, jolle on määritelty virhetilanne (eli kun n<0) joka "nostaa" runtime_errorin. 
Tällöin tarvitaan <b>stdexcept</b> kirjasto
Funktion toteutus on siis seuraava:
<pre>
#include <stdexcept>

int factorial(int n)
{
    if(n<0){
        //jos n<0 nostetaan runtime error
        throw std::runtime_error("n ei saa olla negatiivinen.");
    }
    else{
        int result=1;
        for(int row=1; row<=n; row++){
            result= row*result;
        }
        return result;
    }
}

</pre>
Tällaista metodia kutsuttaessa kannattaa käyttää <b>try-catch rakennetta</b> seuraavasti:
<pre>
    //jos try-lohkossa nousee runtime error, hypätään catch-lohkoon
    try {
        result = factorial(num);
        cout << "Luvun " << num << " kertoma = " << result << endl;
    } catch (runtime_error& e) {
        cout << "Error: " << e.what() << endl;
    }
</pre>