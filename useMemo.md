
### Qué es y para qué sirve useMemo?

useMemo es una función que nos permite memorizar un valor, y que se ejecuta sólo cuando el valor es
diferente al que ya se había memorizado. Por ejemplo, si tenemos una función que calcula el
número de elementos de un array, y que se ejecuta sólo cuando el array cambia, podemos usar
useMemo para memorizar el resultado de la función y no volver a calcularlo.

Si no utilizaramos useMemo en este ejemplo, siempre que nuestro componente se renderizase nuevamente,
se volvería a ejecutar la función para calcular el número de elementos del array. Esto es ineficiente
y podría causar una sobrecarga de procesamiento. Usando useMemo, evitamos que se vuelva a ejecutar la función
si la dependencia que le pasamos a useMemo no ha cambiado.

### Casos de uso de useMemo.

- Cuando tenemos una función pesada y lenta que no queremos que se re-ejecute cada vez que se renderice
  su componente y en cambio sólo queremos que se ejecute cuando realmente necesitemos su valor.
- Cuando queramos asegurarnos de que la referencia a un objeto o un array sea exactamente la misma
  que fue en la última vez que se renderizó el componente.

### Sabiendo lo bueno que es useMemo, se debería usar siempre?

No, principalmente porque useMemo si bien hace que la aplicación memorice lo que le estás pasando,
no deja de ser una función más que es llamada siempre que se renderiza el componente, por lo tanto
genera carga en el procesamiento de la aplicación.

Por eso, lo mejor es usar useMemo cuando la función es realmente lenta y necesitemos mejorar el performance de la app.
