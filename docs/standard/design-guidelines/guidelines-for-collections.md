---
title: Instrucciones para colecciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9eea60dafef508748df53e23c211f5778250e7f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="guidelines-for-collections"></a>Instrucciones para colecciones
Cualquier tipo que se ha diseñado específicamente para manipular un grupo de objetos que tienen algunas características comunes puede considerarse una colección. Casi siempre es adecuado para estos tipos implementar <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, por lo que en esta sección consideramos solo tipos que implementan una o ambas de estas interfaces como colecciones.  
  
 **X DO NOT** usar colecciones débilmente tipadas en las API públicas.  
  
 El tipo de todos los valores devueltos y parámetros que representan elementos de la colección debe ser el tipo de elemento exacto, no en cualquiera de sus tipos base (Esto se aplica solo a los miembros públicos de la colección).  
  
 **X DO NOT** usar <xref:System.Collections.ArrayList> o <xref:System.Collections.Generic.List%601> en las API públicas.  
  
 Estos tipos son estructuras de datos diseñadas para su uso en la implementación interna, no en las API públicas. `List<T>`está optimizado para rendimiento y potencia a costa de cleanness de la API y la flexibilidad. Por ejemplo, si devuelve `List<T>`, no nunca podrá recibir notificaciones cuando el código de cliente modifica la colección. Además, `List<T>` expone muchos miembros, como <xref:System.Collections.Generic.List%601.BinarySearch%2A>, que no son útiles o aplicables en muchos escenarios. Las dos secciones siguientes describen los tipos (abstracciones) diseñados específicamente para su uso en las API públicas.  
  
 **X DO NOT** usar `Hashtable` o `Dictionary<TKey,TValue>` en las API públicas.  
  
 Estos tipos son estructuras de datos diseñadas para su uso en la implementación interna. Deben usar las API públicas <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`, o un tipo personalizado que se implementa una o ambas de las interfaces.  
  
 **X DO NOT** usar <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>, o cualquier otro tipo que implementa alguna de estas interfaces, excepto como el tipo de valor devuelto de un `GetEnumerator` método.  
  
 Devolver los enumeradores de métodos distintos de los tipos `GetEnumerator` no se puede usar con el `foreach` instrucción.  
  
 **X DO NOT** implementar ambas `IEnumerator<T>` y `IEnumerable<T>` en el mismo tipo. Lo mismo se aplica a las interfaces no genéricas `IEnumerator` y `IEnumerable`.  
  
## <a name="collection-parameters"></a>Colección de parámetros  
 **✓ HACER** usar los posibles tipo especializado mínimos como un tipo de parámetro. Mayoría de los miembros que toma las colecciones como parámetros utilizan la `IEnumerable<T>` interfaz.  
  
 **X evitar** con <xref:System.Collections.Generic.ICollection%601> o <xref:System.Collections.ICollection> como un parámetro para tener acceso a la `Count` propiedad.  
  
 En su lugar, considere el uso de `IEnumerable<T>` o `IEnumerable` y dinámicamente comprobando si el objeto implementa `ICollection<T>` o `ICollection`.  
  
## <a name="collection-properties-and-return-values"></a>Propiedades de la colección y los valores devueltos  
 **X DO NOT** proporcionan propiedades configurables de recopilación.  
  
 Los usuarios pueden reemplazar el contenido de la colección si elimina primero la colección y, a continuación, agregar el nuevo contenido. Si reemplaza toda la colección es un escenario común, considere la posibilidad de proporcionar el `AddRange` método en la colección.  
  
 **✓ HACER** usar `Collection<T>` o una subclase de `Collection<T>` para propiedades o devuelven valores que representan las colecciones de lectura/escritura.  
  
 Si `Collection<T>` no cumple algunos requisitos (por ejemplo, la colección no debe implementar <xref:System.Collections.IList>), utilizar una colección personalizada implementando `IEnumerable<T>`, `ICollection<T>`, o <xref:System.Collections.Generic.IList%601>.  
  
 **✓ HACER** usar <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, una subclase de `ReadOnlyCollection<T>`, o en casos poco frecuentes `IEnumerable<T>` para propiedades o devuelven valores que representan colecciones de solo lectura.  
  
 Normalmente, es preferible `ReadOnlyCollection<T>`. Si no tiene algún requisito (p. ej., no debe implementar la colección `IList`), utilice una colección personalizada mediante la implementación `IEnumerable<T>`, `ICollection<T>`, o `IList<T>`. Si implementa una colección personalizada de solo lectura, implementar `ICollection<T>.ReadOnly` devuelva el valor false.  
  
 En caso de que esté seguro de que el único escenario alguna vez desea admitir iteración de solo avance, simplemente puede usar `IEnumerable<T>`.  
  
 **✓ Considere la posibilidad de** mediante subclases de las colecciones genéricas de base en lugar de usar directamente las colecciones.  
  
 Esto permite para un nombre más adecuado y agregar los miembros de aplicación auxiliar que no están presentes en los tipos de colección base. Esto es especialmente aplicable a las API de alto nivel.  
  
 **✓ Considere la posibilidad de** devolver una subclase de `Collection<T>` o `ReadOnlyCollection<T>` de propiedades y métodos utilizados con mucha frecuencia.  
  
 Esto hará que sea posible para agregar métodos auxiliares o cambie la implementación de la colección en el futuro.  
  
 **✓ Considere la posibilidad de** con una colección con clave si los elementos almacenados en la colección tienen claves únicas (nombres, Id., etcetera). Colecciones con claves son colecciones que se pueden indizar por un entero y una clave y se implementan normalmente mediante la adquisición de `KeyedCollection<TKey,TItem>`.  
  
 Colecciones con claves normalmente tienen una superficie de memoria mayor y no deben usarse si la sobrecarga de memoria supera con creces las ventajas de tener las claves.  
  
 **X DO NOT** devuelven valores null de propiedades de la colección o de métodos que devuelven colecciones. Devuelve una colección vacía o una matriz vacía en su lugar.  
  
 La regla general es que deben ser nulos y vacías (0) colecciones o matrices tratan de la misma.  
  
### <a name="snapshots-versus-live-collections"></a>Instantáneas frente a colecciones en vivo  
 Que representa un estado en algún momento en el tiempo de colecciones se denominan colecciones de instantánea. Por ejemplo, una colección que contiene filas devueltas de una consulta de base de datos sería una instantánea. Colecciones que siempre representan el estado actual se denominan colecciones en vivo. Por ejemplo, una colección de `ComboBox` elementos es una colección en vivo.  
  
 **X DO NOT** devuelven colecciones de instantánea de propiedades. Las propiedades deberían devolver colecciones en vivo.  
  
 Captadores de propiedades deberían ser operaciones muy ligeras. Devuelve una instantánea requiere la creación de una copia de una colección interna en una operación o (n).  
  
 **✓ HACER** utilizar una colección de instantáneas o activo `IEnumerable<T>` (o su subtipo) para representar las colecciones son volátiles (es decir, que puede cambiar sin modificar explícitamente la colección).  
  
 En general, todas las colecciones que representa un recurso compartido (por ejemplo, los archivos en un directorio) son volátiles. Dichas colecciones son muy difícil o imposible implementar como colecciones en vivo, a menos que la implementación es simplemente un enumerador de solo avance.  
  
## <a name="choosing-between-arrays-and-collections"></a>Elegir entre las matrices y colecciones  
 **✓ HACER** preferir las colecciones de matrices.  
  
 Las colecciones proporcionan más control sobre el contenido, pueden evolucionar con el tiempo y resultan más útiles. Además, usar matrices para escenarios de solo lectura no se recomienda porque el costo de la clonación de la matriz es prohibitivo. Los estudios de facilidad de uso han demostrado que algunos desarrolladores sienten más cómodos con las API basadas en la colección.  
  
 Sin embargo, si va a desarrollar las API de bajo nivel, podría ser mejor usar matrices para escenarios de lectura y escritura. Las matrices tienen una superficie de memoria menor, lo que ayuda a reducir el espacio de trabajo, y acceso a elementos de una matriz es más rápido porque está optimizado en tiempo de ejecución.  
  
 **✓ Considere la posibilidad de** utilizar matrices en las API de bajo nivel para minimizar el consumo de memoria y maximizar el rendimiento.  
  
 **✓ HACER** usar matrices de bytes en lugar de colecciones de bytes.  
  
 **X DO NOT** usar matrices de propiedades si la propiedad tendría que volver a una nueva matriz (p. ej., una copia de una matriz interna) cada vez que se llama al captador de propiedad.  
  
## <a name="implementing-custom-collections"></a>Implementar colecciones personalizadas  
 **✓ Considere la posibilidad de** heredar `Collection<T>`, `ReadOnlyCollection<T>`, o `KeyedCollection<TKey,TItem>` al diseñar nuevas recopilaciones.  
  
 **✓ HACER** implementar `IEnumerable<T>` al diseñar nuevas recopilaciones. Considere la posibilidad de implementar `ICollection<T>` o incluso `IList<T>` siempre que tenga sentido.  
  
 Al implementar este tipo de colección personalizado, siguen el patrón de API establecido por `Collection<T>` y `ReadOnlyCollection<T>` lo más fielmente posible. Es decir, implementar los mismos miembros explícitamente, el nombre de los parámetros como el nombre de estas dos colecciones usarlas y así sucesivamente.  
  
 **✓ Considere la posibilidad de** implementar interfaces de colección no genérica (`IList` y `ICollection`) si la colección a menudo se pasará a las API teniendo estas interfaces como entrada.  
  
 **X evitar** implementar interfaces de colección de tipos con API complejas que no está relacionado con el concepto de una colección.  
  
 **X DO NOT** heredar de colecciones no genéricas de base como `CollectionBase`. Use `Collection<T>`, `ReadOnlyCollection<T>`, y `KeyedCollection<TKey,TItem>` en su lugar.  
  
### <a name="naming-custom-collections"></a>Nomenclatura de recopilaciones personalizadas  
 Colecciones (los tipos que implementan `IEnumerable`) se crean principalmente por dos razones: (1) para crear una nueva estructura de datos con operaciones específicas de la estructura y, a menudo diferentes características de rendimiento de las estructuras de datos existentes (p. ej., <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>) y (2) para crear una colección especializada que contiene un conjunto específico de elementos (p. ej., <xref:System.Collections.Specialized.StringCollection>). Estructuras de datos se usan con mayor frecuencia en la implementación interna de las aplicaciones y bibliotecas. Colecciones especializadas son principalmente que se expondrán en API (como tipos de propiedad y los parámetros).  
  
 **✓ HACER** utilizar el sufijo "Diccionario" en los nombres de abstracciones implementar `IDictionary` o `IDictionary<TKey,TValue>`.  
  
 **✓ HACER** utilizar el sufijo "Collection" en los nombres de tipos que implementan `IEnumerable` (o cualquiera de sus descendientes) y que representa una lista de elementos.  
  
 **✓ HACER** usar el nombre de la estructura de datos adecuado para estructuras de datos personalizadas.  
  
 **X evitar** utilizar los sufijos de lo que implica la implementación concreta, como "LinkedList" o "Tabla hash," en los nombres de abstracciones de la colección.  
  
 **Considere la posibilidad de ✓** agregando el prefijo de nombres de la colección con el nombre del tipo de elemento. Por ejemplo, una colección que almacena elementos de tipo `Address` (implementar `IEnumerable<Address>`) deben tener un nombre `AddressCollection`. Si el tipo de elemento es una interfaz, la "I" prefijo del elemento se puede omitir el tipo. Por lo tanto, una colección de <xref:System.IDisposable> elementos pueden llamarse `DisposableCollection`.  
  
 **✓ Considere la posibilidad de** utilizar el prefijo "ReadOnly" en los nombres de colecciones de solo lectura si una colección de escritura correspondiente podría agregarse o no existe en el marco de trabajo.  
  
 Por ejemplo, debe llamarse una colección de solo lectura de cadenas `ReadOnlyStringCollection`.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
