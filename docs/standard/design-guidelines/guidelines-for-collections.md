---
title: Instrucciones para colecciones
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
author: KrzysztofCwalina
ms.openlocfilehash: 12f086ac92b449e074b9d39a563a20a3ebf2ff26
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145587"
---
# <a name="guidelines-for-collections"></a>Instrucciones para colecciones
Cualquier tipo que se ha diseñado específicamente para manipular un grupo de objetos que tienen alguna característica común puede considerarse una colección. Casi siempre es adecuado para estos tipos implementar <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, por lo que en esta sección se considere sólo tipos que implementan una o ambas de estas interfaces para ser colecciones.  
  
 **X DO NOT** usar colecciones débilmente tipadas en las API públicas.  
  
 El tipo de todos los valores devueltos y parámetros que representan elementos de la colección debe ser el tipo de elemento exactos, no en cualquiera de sus tipos base (Esto se aplica solo a los miembros públicos de la colección).  
  
 **X DO NOT** usar <xref:System.Collections.ArrayList> o <xref:System.Collections.Generic.List%601> en las API públicas.  
  
 Estos tipos son estructuras de datos diseñadas para usarse en la implementación interna, no en las API públicas. `List<T>` está optimizado para rendimiento y potencia a costa de cleanness de las API y flexibilidad. Por ejemplo, si devuelves `List<T>`, no nunca podrá recibir notificaciones cuando el código de cliente modifica la colección. Además, `List<T>` expone muchos miembros, como <xref:System.Collections.Generic.List%601.BinarySearch%2A>, que no son útiles o aplicable en muchos escenarios. Las dos secciones siguientes describen tipos (abstracciones) diseñados específicamente para su uso en las API públicas.  
  
 **X DO NOT** usar `Hashtable` o `Dictionary<TKey,TValue>` en las API públicas.  
  
 Estos tipos son estructuras de datos diseñadas para usarse en la implementación interna. Deben usar las API públicas <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`, o un tipo personalizado que se implementa una o ambas de las interfaces.  
  
 **X DO NOT** usar <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>, o cualquier otro tipo que implementa alguna de estas interfaces, excepto como el tipo de valor devuelto de un `GetEnumerator` método.  
  
 Devolver los enumeradores de métodos distintos de los tipos `GetEnumerator` no se puede usar con el `foreach` instrucción.  
  
 **X DO NOT** implementar ambas `IEnumerator<T>` y `IEnumerable<T>` en el mismo tipo. Lo mismo se aplica a las interfaces no genéricas `IEnumerator` y `IEnumerable`.  
  
## <a name="collection-parameters"></a>Colección de parámetros  
 **✓ DO** usar los posibles tipo especializado mínimos como un tipo de parámetro. Mayor número de miembros teniendo colecciones como parámetros utilizan la `IEnumerable<T>` interfaz.  
  
 **X AVOID** con <xref:System.Collections.Generic.ICollection%601> o <xref:System.Collections.ICollection> como un parámetro para tener acceso a la `Count` propiedad.  
  
 En su lugar, considere el uso de `IEnumerable<T>` o `IEnumerable` y la comprobación de forma dinámica si el objeto implementa `ICollection<T>` o `ICollection`.  
  
## <a name="collection-properties-and-return-values"></a>Propiedades de la colección y valores devueltos  
 **X DO NOT** proporcionan propiedades configurables de recopilación.  
  
 Los usuarios pueden reemplazar el contenido de la colección por borrar la colección en primer lugar y, a continuación, agregar el nuevo contenido. Si reemplaza toda la colección es un escenario común, considere la posibilidad de proporcionar el `AddRange` método en la colección.  
  
 **✓ DO** usar `Collection<T>` o una subclase de `Collection<T>` para propiedades o devuelven valores que representan las colecciones de lectura/escritura.  
  
 Si `Collection<T>` no cumple el requisito de algunos (por ejemplo, la colección no debe implementar <xref:System.Collections.IList>), utilice una colección personalizada implementando `IEnumerable<T>`, `ICollection<T>`, o <xref:System.Collections.Generic.IList%601>.  
  
 **✓ DO** usar <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, una subclase de `ReadOnlyCollection<T>`, o en casos poco frecuentes `IEnumerable<T>` para propiedades o devuelven valores que representan colecciones de solo lectura.  
  
 En general, se prefiere `ReadOnlyCollection<T>`. Si no tiene algún requisito (por ejemplo, la colección no debe implementar `IList`), utilice una colección personalizada implementando `IEnumerable<T>`, `ICollection<T>`, o `IList<T>`. Si implementa una colección de solo lectura personalizada, implementar `ICollection<T>.IsReadOnly` para devolver `true`.  
  
 En caso de que esté seguro de que el único escenario en que alguna vez desea admitir iteración de solo avance, puede usar simplemente `IEnumerable<T>`.  
  
 **✓ CONSIDER** mediante subclases de las colecciones genéricas de base en lugar de usar directamente las colecciones.  
  
 Esto permite para un nombre más adecuado y agregar miembros auxiliares que no están presentes en los tipos de colección base. Esto es especialmente aplicable a las API de alto nivel.  
  
 **✓ CONSIDER** devolver una subclase de `Collection<T>` o `ReadOnlyCollection<T>` de propiedades y métodos utilizados con mucha frecuencia.  
  
 Esto hará posible que le agregue métodos auxiliares o cambiar la implementación de la colección en el futuro.  
  
 **✓ CONSIDER** con una colección con clave si los elementos almacenados en la colección tienen claves únicas (nombres, Id., etcetera). Colecciones con claves son colecciones que se pueden indizar por entero y una clave y se implementan normalmente mediante la herencia de `KeyedCollection<TKey,TItem>`.  
  
 Colecciones con claves normalmente tienen una mayor superficie de memoria y no deben usarse si la sobrecarga de memoria supera las ventajas de tener las claves.  
  
 **X DO NOT** devuelven valores null de propiedades de la colección o de métodos que devuelven colecciones. Devuelve una colección vacía o una matriz vacía en su lugar.  
  
 La regla general es que deben ser null y vacías colecciones (elemento 0) o matrices tratan de la misma.  
  
### <a name="snapshots-versus-live-collections"></a>Instantáneas frente a las colecciones en vivo  
 Que representa un estado en algún momento en el tiempo de colecciones se denominan colecciones de instantánea. Por ejemplo, una colección que contiene las filas devueltas de una consulta de base de datos sería una instantánea. Las colecciones que siempre representan el estado actual se denominan colecciones en vivo. Por ejemplo, una colección de `ComboBox` elementos es una colección en vivo.  
  
 **X DO NOT** devuelven colecciones de instantánea de propiedades. Las propiedades deben devolver colecciones en vivo.  
  
 Captadores de propiedades deberían ser operaciones muy ligeras. Devuelve una instantánea requiere la creación de una copia de una colección interna en una operación o (n).  
  
 **✓ DO** utilizar una colección de instantáneas o activo `IEnumerable<T>` (o su subtipo) para representar las colecciones son volátiles (es decir, que puede cambiar sin modificar explícitamente la colección).  
  
 En general, todas las colecciones que representa un recurso compartido (por ejemplo, los archivos en un directorio) son volátiles. Estas colecciones son muy difícil o imposible implementar como colecciones en vivo a menos que la implementación es simplemente un enumerador de solo avance.  
  
## <a name="choosing-between-arrays-and-collections"></a>Elegir entre las matrices y colecciones  
 **✓ DO** preferir las colecciones de matrices.  
  
 Las colecciones proporcionan más control sobre el contenido, pueden evolucionar con el tiempo y son más fáciles de utilizar. Además, usar matrices para escenarios de solo lectura no se recomienda porque el costo de clonación de la matriz es prohibitivo. Los estudios de facilidad de uso han demostrado que algunos desarrolladores sientan más cómodos con las API basadas en la colección.  
  
 Sin embargo, si está desarrollando la API de bajo nivel, podría ser mejor usar matrices para escenarios de lectura y escritura. Las matrices tienen una menor superficie de memoria, lo que ayuda a reducir el espacio de trabajo, y acceso a los elementos de una matriz es más rápido porque está optimizado por el tiempo de ejecución.  
  
 **✓ CONSIDER** utilizar matrices en las API de bajo nivel para minimizar el consumo de memoria y maximizar el rendimiento.  
  
 **✓ DO** usar matrices de bytes en lugar de colecciones de bytes.  
  
 **X DO NOT** usar matrices de propiedades si la propiedad tendría que volver a una nueva matriz (p. ej., una copia de una matriz interna) cada vez que se llama al captador de propiedad.  
  
## <a name="implementing-custom-collections"></a>Implementación de recopilaciones personalizadas  
 **✓ CONSIDER** heredar `Collection<T>`, `ReadOnlyCollection<T>`, o `KeyedCollection<TKey,TItem>` al diseñar nuevas recopilaciones.  
  
 **✓ DO** implementar `IEnumerable<T>` al diseñar nuevas recopilaciones. Considere la posibilidad de implementar `ICollection<T>` o incluso `IList<T>` donde tenga sentido.  
  
 Al implementar este tipo de colección personalizada, siguen el patrón de API que se establece mediante la `Collection<T>` y `ReadOnlyCollection<T>` lo máximo posible. Es decir, implementar explícitamente los mismos miembros, nombre de los parámetros como el nombre de estas dos colecciones de ellos y así sucesivamente.  
  
 **✓ CONSIDER** implementar interfaces de colección no genérica (`IList` y `ICollection`) si la colección a menudo se pasará a las API teniendo estas interfaces como entrada.  
  
 **X AVOID** implementar interfaces de colección de tipos con API complejas que no está relacionado con el concepto de una colección.  
  
 **X DO NOT** heredar de colecciones no genéricas de base como `CollectionBase`. Use `Collection<T>`, `ReadOnlyCollection<T>`, y `KeyedCollection<TKey,TItem>` en su lugar.  
  
### <a name="naming-custom-collections"></a>Nomenclatura de recopilaciones personalizadas  
 Colecciones (los tipos que implementan `IEnumerable`) se crean principalmente por dos motivos: (1) para crear una nueva estructura de datos con operaciones específicas de la estructura y a menudo diferentes características de rendimiento que las estructuras de datos existente (por ejemplo, <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>) y (2) para crear una colección especializada para que contiene un conjunto específico de elementos (por ejemplo, <xref:System.Collections.Specialized.StringCollection>). Estructuras de datos se suelen usar en la implementación interna de aplicaciones y bibliotecas. Colecciones especializadas son principalmente para exponerse en API (como tipos de propiedad y los parámetros).  
  
 **✓ DO** utilizar el sufijo "Diccionario" en los nombres de abstracciones implementar `IDictionary` o `IDictionary<TKey,TValue>`.  
  
 **✓ DO** utilizar el sufijo "Collection" en los nombres de tipos que implementan `IEnumerable` (o cualquiera de sus descendientes) y que representa una lista de elementos.  
  
 **✓ DO** usar el nombre de la estructura de datos adecuado para estructuras de datos personalizadas.  
  
 **X AVOID** utilizar los sufijos de lo que implica la implementación concreta, como "LinkedList" o "Tabla hash," en los nombres de abstracciones de la colección.  
  
 **✓ CONSIDER** agregando el prefijo de nombres de la colección con el nombre del tipo de elemento. Por ejemplo, una colección almacenar elementos de tipo `Address` (implementar `IEnumerable<Address>`) debe denominarse `AddressCollection`. Si el tipo de elemento es una interfaz, la "I" prefijo del elemento de tipo se puede omitir. Por lo tanto, una colección de <xref:System.IDisposable> elementos pueden llamarse `DisposableCollection`.  
  
 **✓ CONSIDER** utilizar el prefijo "ReadOnly" en los nombres de colecciones de solo lectura si una colección de escritura correspondiente podría agregarse o no existe en el marco de trabajo.  
  
 Por ejemplo, se debe llamar a una colección de solo lectura de cadenas `ReadOnlyStringCollection`.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
