---
title: "Directrices para las colecciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Directrices para las colecciones
Cualquier tipo que se ha diseñado específicamente para manipular un grupo de objetos que tienen algunas características comunes puede considerarse una colección. Casi siempre es adecuado para estos tipos implementar <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, por lo que en esta sección se considere sólo tipos que implementan una o ambas de las interfaces que las colecciones.  
  
 **X no** usar colecciones débilmente tipadas en las API públicas.  
  
 El tipo de todos los valores devueltos y parámetros que representan elementos de la colección debe ser el tipo de artículo exacto, no en cualquiera de sus tipos base \(se aplica sólo a los miembros públicos de la colección\).  
  
 **X no** use <xref:System.Collections.ArrayList> o <xref:System.Collections.Generic.List%601> en las API públicas.  
  
 Estos tipos son estructuras de datos diseñadas para utilizarse en la implementación interna, no en las API públicas.`List<T>` está optimizado para rendimiento y potencia a costa de cleanness de la API y la flexibilidad. Por ejemplo, si devuelve `List<T>`, no siempre será capaz de recibir notificaciones cuando el código de cliente modifica la colección. Además, `List<T>` expone muchos miembros, como <xref:System.Collections.Generic.List%601.BinarySearch%2A>, que no son útiles o aplicable en muchos escenarios. Las dos secciones siguientes describen los tipos \(abstracciones\) diseñados específicamente para su uso en las API públicas.  
  
 **X no** use `Hashtable` o `Dictionary<TKey,TValue>` en las API públicas.  
  
 Estos tipos son estructuras de datos diseñadas para utilizarse en la implementación interna. Deben utilizar las API públicas <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`, o un tipo personalizado que se implementa una o ambas de las interfaces.  
  
 **X no** use <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>, o cualquier otro tipo que implementa alguna de estas interfaces, excepto que el tipo devuelto de un `GetEnumerator` \(método\).  
  
 Devolver los enumeradores de métodos distintos de los tipos `GetEnumerator` no puede utilizarse con el `foreach` instrucción.  
  
 **X no** implementan `IEnumerator<T>` y `IEnumerable<T>` en el mismo tipo. Lo mismo se aplica a las interfaces no genéricas `IEnumerator` y `IEnumerable`.  
  
## Colección de parámetros  
 **✓ hacer** utilizar el posible tipo menos especializados como un tipo de parámetro. Mayoría de los miembros teniendo colecciones como parámetros utilizan la `IEnumerable<T>` interfaz.  
  
 **Evitar X** con <xref:System.Collections.Generic.ICollection%601> o <xref:System.Collections.ICollection> como un parámetro para tener acceso a la `Count` propiedad.  
  
 En su lugar, considere el uso de `IEnumerable<T>` o `IEnumerable` y comprobar dinámicamente si el objeto implementa `ICollection<T>` o `ICollection`.  
  
## Propiedades de la colección y los valores devueltos  
 **X no** proporciona propiedades configurables de colección.  
  
 Los usuarios pueden reemplazar el contenido de la colección de borrar la colección en primer lugar y, a continuación, agregando el nuevo contenido. Si un escenario común es reemplazar toda la colección, considere la posibilidad de proporcionar el `AddRange` método en la colección.  
  
 **✓ hacer** use `Collection<T>` o una subclase de `Collection<T>` para propiedades o devuelven valores que representan colecciones de lectura y escritura.  
  
 Si `Collection<T>` no se cumple algún requisito \(por ejemplo, la colección no debe implementar <xref:System.Collections.IList>\), utilice una colección personalizada implementando `IEnumerable<T>`, `ICollection<T>`, o <xref:System.Collections.Generic.IList%601>.  
  
 **✓ hacer** utilizar <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, una subclase de `ReadOnlyCollection<T>`, o en casos excepcionales `IEnumerable<T>` para propiedades o devuelven valores que representan colecciones de solo lectura.  
  
 En general, se prefiere `ReadOnlyCollection<T>`. Si no se cumple algún requisito \(por ejemplo, la colección no debe implementar `IList`\), utilice una colección personalizada implementando `IEnumerable<T>`, `ICollection<T>`, o `IList<T>`. Si implementa una colección personalizada de sólo lectura, implementar `ICollection<T>.ReadOnly` devuelva false.  
  
 En caso de que esté seguro de que el único escenario preguntado admite la iteración de solo avance, simplemente puede usar `IEnumerable<T>`.  
  
 **✓, considere la posibilidad de** mediante subclases de las colecciones genéricas de bases en lugar de usar directamente las colecciones.  
  
 Esto permite un mejor nombre y agregar miembros auxiliares que no están presentes en los tipos de colección base. Esto es especialmente aplicable a la API de alto nivel.  
  
 **✓ considere** devolver una subclase de `Collection<T>` o `ReadOnlyCollection<T>` de propiedades y métodos utilizados con mucha frecuencia.  
  
 Esto hará posible para agregar métodos auxiliares o cambiar la implementación de la colección en el futuro.  
  
 **✓, considere la posibilidad de** mediante una colección con clave si dispone de los elementos almacenados en la colección de claves únicas \(nombres, identificadores, etc.\). Colecciones con claves son colecciones que se pueden indizar por entero y una clave y se implementan normalmente mediante la herencia de `KeyedCollection<TKey,TItem>`.  
  
 Colecciones con claves normalmente tienen superficies de memoria más grandes y no deben utilizarse si la sobrecarga de memoria supera con creces las ventajas de tener las claves.  
  
 **X no** devuelven valores null de las propiedades de colección o de métodos que devuelven colecciones. Devuelve una colección vacía o una matriz vacía en su lugar.  
  
 La regla general es que deben ser nulas y vacías colecciones \(elemento 0\) o matrices tratan de la misma.  
  
### Instantáneas frente a recopilaciones en vivo  
 Que representa un estado en algún momento en el tiempo de colecciones se denominan colecciones de instantánea. Por ejemplo, una colección que contiene filas devueltas de una consulta de base de datos sería una instantánea. Colecciones que siempre representan el estado actual se denominan colecciones en vivo. Por ejemplo, una colección de `ComboBox` elementos es una colección.  
  
 **X no** devuelven colecciones de instantánea de las propiedades. Propiedades deben devolver colecciones en vivo.  
  
 Captadores de propiedades deberían ser operaciones muy ligeras. Devuelve una instantánea requiere la creación de una copia de una colección interna en una operación o \(n\).  
  
 **✓ hacer** utilizar una colección de instantáneas o activo `IEnumerable<T>` \(o su subtipo\) para representar colecciones que son volátiles \(es decir, que puede cambiar sin modificar explícitamente la colección\).  
  
 En general, todas las colecciones que representa un recurso compartido \(por ejemplo, los archivos en un directorio\) son volátiles. Estas colecciones son muy difícil o imposible implementar como colecciones en vivo a menos que la implementación es simplemente un enumerador de sólo avance.  
  
## Elegir entre las matrices y colecciones  
 **✓ hacer** preferir las matrices en colecciones.  
  
 Colecciones de proporcionan más control sobre el contenido, pueden evolucionar con el tiempo y son más fáciles de utilizar. Además, utilizar matrices para escenarios de sólo lectura no se recomienda porque el costo de la clonación de la matriz es prohibitivo. Estudios de uso han demostrado que algunos desarrolladores sientan más cómodos con API basadas en la colección.  
  
 Sin embargo, si está desarrollando la API de bajo nivel, podría ser mejor usar matrices para escenarios de lectura y escritura. Las matrices tienen una superficie de memoria menor, lo que ayuda a reducir el espacio de trabajo, y acceso a los elementos de una matriz es más rápido porque está optimizado en tiempo de ejecución.  
  
 **✓ considere** utilizar matrices en las API de bajo nivel para minimizar el consumo de memoria y maximizar el rendimiento.  
  
 **✓ hacer** utilizar matrices de bytes en lugar de colecciones de bytes.  
  
 **X no** usar matrices de propiedades, si la propiedad tendría que devolver una nueva matriz \(por ejemplo, una copia de una matriz interna\) cada vez que se llama al captador de propiedad.  
  
## Implementar colecciones personalizadas  
 **✓ considere** heredar `Collection<T>`, `ReadOnlyCollection<T>`, o `KeyedCollection<TKey,TItem>` al diseñar nuevas colecciones.  
  
 **✓ hacer** implementar `IEnumerable<T>` al diseñar nuevas colecciones. Considere la implementación de `ICollection<T>` o incluso `IList<T>` donde tenga sentido.  
  
 Al implementar este tipo de colección personalizado, siguen el patrón de API establecido por `Collection<T>` y `ReadOnlyCollection<T>` tan cerca como sea posible. Es decir, implementan los mismos miembros explícitamente, el nombre de los parámetros como el nombre de estas dos colecciones de ellos y así sucesivamente.  
  
 **✓ considere** implementar interfaces de colección no genérica \(`IList` y `ICollection`\) si la colección a menudo se pasará a la API teniendo estas interfaces como entrada.  
  
 **Evitar X** implementar interfaces de colección en tipos con API complejas no está relacionado con el concepto de una colección.  
  
 **X no** heredan de colecciones no genéricas de bases como `CollectionBase`. Use `Collection<T>`, `ReadOnlyCollection<T>`, y `KeyedCollection<TKey,TItem>` en su lugar.  
  
### Nombres colecciones personalizadas  
 Colecciones \(tipos que implementan `IEnumerable`\) se crean principalmente por dos razones: \(1\) para crear una nueva estructura de datos con operaciones específicas de la estructura y, a menudo diferentes características de rendimiento de las estructuras de datos existentes \(por ejemplo,  <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>\) y \(2\) para crear una colección especializada que contiene un conjunto específico de elementos \(por ejemplo,  <xref:System.Collections.Specialized.StringCollection>\). Estructuras de datos se usan normalmente en la implementación interna de aplicaciones y bibliotecas. Colecciones especializadas son principalmente exponerse en la API \(como tipos de parámetro y de propiedad\).  
  
 **✓ hacer** utilizar el sufijo "Dictionary" en los nombres de abstracciones implementar `IDictionary` o `IDictionary<TKey,TValue>`.  
  
 **✓ hacer** utilizar el sufijo "Collection" en los nombres de tipos que implementan `IEnumerable` \(o cualquiera de sus descendientes\) y que representa una lista de elementos.  
  
 **✓ hacer** utilizar el nombre de la estructura de datos adecuada para estructuras de datos personalizadas.  
  
 **Evitar X** utilizar los sufijos que implica la implementación concreta, como "LinkedList" o "Tabla hash," en los nombres de abstracciones de la colección.  
  
 **✓, considere la posibilidad de** un prefijo a nombres de la colección con el nombre del tipo de elemento. Por ejemplo, una colección que almacena elementos de tipo `Address` \(implementar `IEnumerable<Address>`\) debe denominarse `AddressCollection`. Si el tipo de elemento es una interfaz, el prefijo "I" del elemento de tipo se puede omitir. Por lo tanto, una colección de <xref:System.IDisposable> elementos pueden llamarse `DisposableCollection`.  
  
 **✓ considere** con el prefijo "ReadOnly" en los nombres de colecciones de sólo lectura si la colección grabable correspondiente podría agregarse o ya existe en el marco de trabajo.  
  
 Por ejemplo, debe llamarse una colección de solo lectura de cadenas `ReadOnlyStringCollection`.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)