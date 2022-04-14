
### useContext con Typescript.

De forma resumida, un contexto usando Typescript se hace de la siguiente manera:

1. Crear el Context y Provider como lo haría en Javascript.
2. Si no usa un valor por defecto, necesito proveerle una interfaz.
3. Consumir el contexto con useContext.
4. Los tipos de Typescript van a ser automticamente inferidos de los valores por defecto o la interfaz proveida.

#### Como hacer un contexto sin valor por defecto?

Primero hay que crear una interfaz para nuestro contexto y asignarsela.
Una vez hecho esto, podemos elegir entre darle un valor por defecto, o de lo contrario envolver nuestra interfaz
en la función helper **Partial**.
  
  ```typescript
  interface Contexto {
    valor: string;
  }
  
  const Contexto: createContext<Partial<Contexto>>({});
  ```
  
**Hay un problema con este approach**, y es que todas las propiedades del contexto son opcionales,
forzandonos a acceder a ellas con el opcional: *?*. Por esta razón, es mejor evitar usar el **Partial**
y definir todas las propiedades requiridas en los valores por defecto.
