# Nivel 1.3

Técnicas de previsión

Sesión 08/11/2019

* aty Zt son contemporáneas, por lo que no podemos conocer at si no disponemos de Zt. Si realizamos una estimación de Zt \(\), podemos considerar que la media del ruido blanco es 0, por lo que at será nula.

## Ejercicio 7.1.

* A la serie se le ha aplicado un diferenciador regular \(decalado de 1 instante de tiempo\) y un diferenciador estacional \(decalado de 1 estacionalidad, que en este caso es de 24\). Por lo tanto, la serie decalada empezaría en el instante 26.
* Es importante ver cómo para t=121 nos estamos apoyando en valores reales, mientras que para t=122 nos apoyamos en el valor predicho anterior. Por lo tanto, al no apoyarnos en datos reales, el error aumenta.

No sabemos sin un AR\(p\) es estacionario hasta que lo comprobamos, pero son siempre invertibles.

Un modelo MA\(q\) siempre es estacionario, pero no sabemos si es invertible hasta que lo comprobamos.

En un AR\(p\):

* Si p=1 \|phi\_1\| &lt;1
* Si p=2 debe cumplir estas tres condiciones:
  * Phi\_1+phi\_2&lt;1
  * Phi\_2-phi\_1&lt;1
  * \|Phi\_2\|&lt;1

Si no se cumplen las propiedades de arriba, podemos decir que un modelo \(ya sea AR o ARMA\) no vale, porque no es estacionario.

Hacemos lo mismo para MA\(q\):

* Si q=1; \|thita\_1\|&lt;1
* Si q=2;
  * Thita\_1+thita\_2&lt;1
  * Thita\_2-thita\_1&lt;1
  * \|thita\_\_2\|&lt;1

Si el modelo no cumple las condiciones de arriba, el modelo no sería invertible.

Importante: Statgraphics haría el cálculo igualmente, aunque no se cumpliesen las condiciones anteriores. Somos nosotros los que tenemos que discriminar si se dan las condiciones para aplicar el ARIMA.

## Tema 3.

### Validación del modelo

* La etapa de validación consiste en identificar si los residuos son o no ruido blanco. No siempre es posible conseguir que los residuos sean ruido blanco.
* ¿Qué significa que todos los residuos sean ruido blanco? Que toda la estructura de correlación de la serie original ha pasado al modelo.
* Si los residuos no son ruido blanco, se puede deber a que hay una componente estacional doble, ARIMA no es capaz de analizar doble estacionalidad.
* Ojo a los apuntes. Cuando habla de fijarse en 6, 8, 10 coeficientes de autocorrelación, es aplicable a series con un periodo estacional 12. Esto se debe a que nos debemos fijar en coeficientes menores que una sola estacionalidad.
* Esto es muy importante:

![](.gitbook/assets/0.png)

* Validación
  * Tenemos que preguntarnos si los residuos son ruido blanco
  * Obtenemos fap y fas para los residuos del modelo. Con ellos, analizamos si los residuos están incorrelacionados \(que es lo que debe pasar\) Test de Portmanteau
  * En el Test de Portmanteau, si tenemos un modelo con Py Q, los grados de libertad de Chi cuadrado tienen que ser K-p-q-P-Q \(Dependerá del ARIMA que hagamos\).
  * Con un coeficiente de autocorrelación simple que está en un k alto, podemos decir que todos los residuos son nulos. Sin embargo, si está en un k muy bajo, no podemos afirmar esto. El test de Box-Pierce no es capaz de hacer esta distinción, por lo que puede llevarnos a conclusiones erróneas. Por ello se utiliza el test de Ljung-Box, que divide los residuos en paquetes, a partir de los cuales el analista puede tomar decisiones.

