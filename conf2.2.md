# Evitando desastres!
![](primera.jpg "primera")
### Errores:
Teniendo que :
Valor exacto: x
Valor aproximado: x'
#### Error absoluto: $$e= |x -x'|$$
#### Error relativo: $$d= \frac{|x -x'|}{x}$$
#### Cifras significativas correctas(csc):
¿Qué son las cifras significativas?
En un número cualquiera, las cifras significativas son todas las que están a
la derecha del primer digito diferente de 0, incluyendo a este primer dígito.
Cuando hablamos de cifras csc hay involucrados dos números , un valor real x y un apoximado x', entonces:
x' tiene k cifras significativas correctas (csc)
en base B si:
$$d= \frac{|x -x'|}{x} \le \frac{1}{2}B^{1-k}$$

#### Cotas para los errores en las AFP
![](segunda.jpg "segunda")

Nunca se puede conocer el error! :-(
	Y cuando se puede,¡NO VALE LA PENA!
	Pero para nuestra suerte Lo importante es conocer la cota
del error.
En una aritmetica flatante tendriamos:
real x = x
aproximado  x' = fl(x)
entonces en cuanto a error absoluto tenemos que:
truncamiento:
$$e=|fi-x| \lt B^{k-p}$$
redomndeo:
$$e=|fi-x| \lt \frac{1}{2}B^{k-p}$$

y en cuanto a error relativo:
truncamiento:
$$ d \le B^{1-p}$$
redomndeo:
$$ d \le  \frac{1}{2}B^{1-p}$$
#### Cancelación catastrófica: pérdida de c.s.c por resta de números parecidos.
Cantidad de cifras significativas: x' tiene r `cifras signicativas correctas en base B` si el error relativo cumple que: $$ e \le  \frac{1}{2}B^{1-r}$$
Se conoce como `Cancelación Catastrofica` a la perdida de csc a partir de una resta de números cercanos
![](cuarta.jpg "cuarta")
Para nuestra suerte hay maneras de evitarlo.
![](tercera.jpg "tercera")
Para evitarlo podemos:
-multiplicar y dividir por la conjugada.
-aplicar desarrollo de serie de Taylor y truncar en algún término apropiado.

#### Estabilidad Numérica: propiedad que mide cuán sensible es un algoritmo a los errores de redondeo.
Si el algoritmo es estable, esos errores se mantienen acotados,
idealmente son menores que el  épsilon de la máquina. Si el algoritmo es
inestable, un peque~no error puede ser desastroso, como en el caso de la raíz de
la parábola.
`Condición de una función`
|La condición de una función describe cuánto puede variar el error en el
resultado de la evaluación de una funcioón, si varía el error en el argumento.
Cómo sabemos cúal es????????
~El error relativo(df) que se comete en la función es:
$$df=\frac{|fx-fx'|}{|fx|} $$
Y el error relativo que se comete al aproximar x por x' es:
$$dx=\frac{|x-x'|}{|x|} $$
Por lo tanto, un medidor de cuánto varía el error relativo de la función cuando
varía el error relativo del argumento se puede describir cómo:
$$\frac{df}{dx}=\frac{\frac{|fx-fx'|}{|fx|}}{\frac{|x-x'|}{|x|}}$$
observando....
si un pequeño error en el argumento provocar un error grande en la función el valor de ese cociente es grande. Por otro lado, si el error en la función es menor que el error en el
argumento, entonces el cociente es un número pequeño. Si los dos errores (el de la función y el del argumento) son similares, el valor del cociente está cercano a uno.
Luego...La condición:
$$cond(f)=max(x.proximo(x'))\frac{\frac{|fx-fx'|}{|fx|}}{\frac{|x-x'|}{|x|}}$$
si f es diferenciable entonces:
$$cond(f)=|\frac{xf'x}{fx}|$$
observando...
un error, por peque~no que sea, en el argumento de la resta, puede traducirse en un error potencialmente infonito! en el resultado ,así que se debería tener cuidado con la resta, sobre todo si lo que se resta son dos
números  cercanos"
![](quinta.jpg "quinta")
#### Estabilidad
una forma de determinar si un método para calcular un valor es estable o no, es comparar la condición de lo que se quiere calcular con la condición de cada una de las funciones involucradas en ese cálculo.
