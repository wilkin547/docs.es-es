---
title: Instrucciones para colecciones
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
ms.openlocfilehash: 50497de6569b448ab036af8a1fbf76a47565e2bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741867"
---
# <a name="guidelines-for-collections"></a>Instrucciones para colecciones
Cualquier tipo diseñado específicamente para manipular un grupo de objetos que tienen alguna característica común se puede considerar una colección. Casi siempre es adecuado para estos tipos implementar <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, por lo que en esta sección solo se tienen en cuenta los tipos que implementan una o ambas interfaces para ser colecciones.

 ❌ no usan colecciones débilmente tipadas en las API públicas.

 El tipo de todos los valores devueltos y los parámetros que representan elementos de colección debe ser el tipo de elemento exacto, no cualquiera de sus tipos base (esto solo se aplica a los miembros públicos de la colección).

 ❌ no usan <xref:System.Collections.ArrayList> ni <xref:System.Collections.Generic.List%601> en las API públicas.

 Estos tipos son estructuras de datos diseñadas para usarse en la implementación interna, no en las API públicas. `List<T>` está optimizado para el rendimiento y potencia a costa de la limpieza de las API y la flexibilidad. Por ejemplo, si devuelve `List<T>`, nunca podrá recibir notificaciones cuando el código de cliente modifique la colección. Además, `List<T>` expone muchos miembros, como <xref:System.Collections.Generic.List%601.BinarySearch%2A>, que no son útiles o son aplicables en muchos escenarios. En las dos secciones siguientes se describen los tipos (abstracciones) diseñados específicamente para su uso en las API públicas.

 ❌ no usan `Hashtable` ni `Dictionary<TKey,TValue>` en las API públicas.

 Estos tipos son estructuras de datos diseñadas para usarse en la implementación interna. Las API públicas deben usar <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`o un tipo personalizado que implementa una o ambas interfaces.

 ❌ no usan <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>o cualquier otro tipo que implemente cualquiera de estas interfaces, excepto como el tipo de valor devuelto de un método de `GetEnumerator`.

 Los tipos que devuelven enumeradores de métodos distintos de `GetEnumerator` no se pueden usar con la instrucción `foreach`.

 ❌ no implementan `IEnumerator<T>` y `IEnumerable<T>` en el mismo tipo. Lo mismo se aplica a las interfaces no genéricas `IEnumerator` y `IEnumerable`.

## <a name="collection-parameters"></a>Parámetros de colección
 ✔️ usar el tipo menos especializado posible como tipo de parámetro. La mayoría de los miembros que toman colecciones como parámetros usan la interfaz `IEnumerable<T>`.

 ❌ evitar el uso de <xref:System.Collections.Generic.ICollection%601> o <xref:System.Collections.ICollection> como parámetro solo para tener acceso a la propiedad `Count`.

 En su lugar, considere la posibilidad de usar `IEnumerable<T>` o `IEnumerable` y comprobar dinámicamente si el objeto implementa `ICollection<T>` o `ICollection`.

## <a name="collection-properties-and-return-values"></a>Propiedades de colección y valores devueltos
 ❌ no proporcionan propiedades de colección que se pueden establecer.

 Los usuarios pueden reemplazar el contenido de la colección borrando primero la colección y, a continuación, agregando el nuevo contenido. Si reemplazar toda la colección es un escenario común, considere la posibilidad de proporcionar el método `AddRange` en la colección.

 ✔️ usar `Collection<T>` o una subclase de `Collection<T>` para propiedades o valores devueltos que representan colecciones de lectura/escritura.

 Si `Collection<T>` no cumple algún requisito (por ejemplo, la colección no debe implementar <xref:System.Collections.IList>), use una colección personalizada implementando `IEnumerable<T>`, `ICollection<T>`o <xref:System.Collections.Generic.IList%601>.

 ✔️ usar <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, una subclase de `ReadOnlyCollection<T>`o, en raras ocasiones, `IEnumerable<T>` para propiedades o valores devueltos que representan colecciones de solo lectura.

 En general, se prefiere `ReadOnlyCollection<T>`. Si no cumple algún requisito (por ejemplo, la colección no debe implementar `IList`), use una colección personalizada implementando `IEnumerable<T>`, `ICollection<T>`o `IList<T>`. Si implementa una colección personalizada de solo lectura, implemente `ICollection<T>.IsReadOnly` para devolver `true`.

 En los casos en los que esté seguro de que el único escenario que desea admitir es la iteración de solo avance, simplemente puede usar `IEnumerable<T>`.

 ✔️ CONSIDERE el uso de subclases de colecciones base genéricas en lugar de usar las colecciones directamente.

 Esto permite un nombre mejor y para agregar miembros auxiliares que no están presentes en los tipos base de la colección. Esto se aplica especialmente a las API de alto nivel.

 ✔️ considere la posibilidad de devolver una subclase de `Collection<T>` o `ReadOnlyCollection<T>` de métodos y propiedades de uso frecuente.

 Esto hará posible agregar métodos auxiliares o cambiar la implementación de la colección en el futuro.

 ✔️ considere la posibilidad de usar una colección con clave si los elementos almacenados en la colección tienen claves únicas (nombres, identificadores, etc.). Las colecciones con clave son colecciones que se pueden indizar por un entero y una clave y se suelen implementar heredando de `KeyedCollection<TKey,TItem>`.

 Las colecciones con clave suelen tener mayor cantidad de memoria y no deben usarse si la sobrecarga de memoria supera las ventajas de tener las claves.

 ❌ no devuelven valores NULL de las propiedades de colección o de métodos que devuelven colecciones. En su lugar, devuelve una colección vacía o una matriz vacía.

 La regla general es que las colecciones o matrices vacías (0 elementos) se deben tratar de la misma forma.

### <a name="snapshots-versus-live-collections"></a>Instantáneas frente a colecciones dinámicas
 Las colecciones que representan un estado en un momento dado se denominan colecciones de instantáneas. Por ejemplo, una colección que contiene filas devueltas por una consulta de base de datos sería una instantánea. Las colecciones que siempre representan el estado actual se denominan colecciones activas. Por ejemplo, una colección de elementos `ComboBox` es una colección dinámica.

 ❌ no devuelven colecciones de instantáneas de propiedades. Las propiedades deben devolver colecciones dinámicas.

 Los captadores de propiedad deben ser operaciones muy ligeras. Devolver una instantánea requiere la creación de una copia de una colección interna en una operación O (n).

 ✔️ usar una colección de instantáneas o un `IEnumerable<T>` en directo (o su subtipo) para representar colecciones que son volátiles (es decir, que pueden cambiar sin modificar explícitamente la colección).

 En general, todas las colecciones que representan un recurso compartido (por ejemplo, los archivos de un directorio) son volátiles. Estas colecciones son muy difíciles o imposibles de implementar como colecciones en directo a menos que la implementación sea simplemente un enumerador de solo avance.

## <a name="choosing-between-arrays-and-collections"></a>Elegir entre matrices y colecciones
 ✔️ prefiere colecciones sobre matrices.

 Las colecciones proporcionan más control sobre el contenido, pueden evolucionar con el tiempo y son más fáciles de usar. Además, no se recomienda el uso de matrices para escenarios de solo lectura porque el costo de clonación de la matriz es prohibitivo. Los estudios de uso han demostrado que algunos desarrolladores se sienten más cómodos con las API basadas en colecciones.

 Sin embargo, si está desarrollando API de bajo nivel, podría ser mejor usar matrices para escenarios de lectura y escritura. Las matrices tienen una superficie de memoria menor, lo que ayuda a reducir el espacio de trabajo y el acceso a los elementos de una matriz es más rápido porque está optimizado por el tiempo de ejecución.

 ✔️ considere la posibilidad de usar matrices en las API de bajo nivel para minimizar el consumo de memoria y maximizar el rendimiento.

 ✔️ usar matrices de bytes en lugar de colecciones de bytes.

 ❌ no utilice matrices para las propiedades si la propiedad tendría que devolver una nueva matriz (por ejemplo, una copia de una matriz interna) cada vez que se llama al captador de propiedad.

## <a name="implementing-custom-collections"></a>Implementar colecciones personalizadas
 ✔️ considere la posibilidad de heredar de `Collection<T>`, `ReadOnlyCollection<T>`o `KeyedCollection<TKey,TItem>` al diseñar nuevas colecciones.

 ✔️ implementar `IEnumerable<T>` al diseñar nuevas colecciones. Considere la posibilidad de implementar `ICollection<T>` o incluso `IList<T>` donde tenga sentido.

 Al implementar dicha colección personalizada, siga el modelo de API establecido por `Collection<T>` y `ReadOnlyCollection<T>` lo más fielmente posible. Es decir, implemente los mismos miembros explícitamente, asigne un nombre a los parámetros como, por ejemplo, los nombres de estas dos colecciones, etc.

 ✔️ considere la posibilidad de implementar interfaces de colección no genéricas (`IList` y `ICollection`) si la colección se va a pasar a menudo a las API que toman estas interfaces como entrada.

 ❌ evitar la implementación de interfaces de colección en tipos con API complejas no relacionadas con el concepto de una colección.

 ❌ no heredan de colecciones base no genéricas como `CollectionBase`. Use `Collection<T>`, `ReadOnlyCollection<T>`y `KeyedCollection<TKey,TItem>` en su lugar.

### <a name="naming-custom-collections"></a>Asignar nombres a colecciones personalizadas
 Las colecciones (tipos que implementan `IEnumerable`) se crean principalmente por dos motivos: (1) para crear una nueva estructura de datos con operaciones específicas de la estructura y, a menudo, distintas características de rendimiento que las estructuras de datos existentes (por ejemplo, <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>) y (2) para crear una colección especializada para contener un conjunto específico de elementos (por ejemplo, <xref:System.Collections.Specialized.StringCollection>) Las estructuras de datos se usan con mayor frecuencia en la implementación interna de aplicaciones y bibliotecas. Las colecciones especializadas se exponen principalmente en las API (como tipos de propiedades y parámetros).

 ✔️ usar el sufijo "Dictionary" en los nombres de las abstracciones que implementan `IDictionary` o `IDictionary<TKey,TValue>`.

 ✔️ usar el sufijo "Collection" en nombres de tipos que implementan `IEnumerable` (o cualquiera de sus descendientes) y que representan una lista de elementos.

 ✔️ usar el nombre de la estructura de datos adecuado para las estructuras de datos personalizadas.

 ❌ evitar el uso de sufijos que impliquen una implementación concreta, como "LinkedList" o "Hashtable", en nombres de abstracciones de colección.

 ✔️ considere la posibilidad de prefijar los nombres de colección con el nombre del tipo de elemento. Por ejemplo, una colección que almacena elementos de tipo `Address` (implementando `IEnumerable<Address>`) debe denominarse `AddressCollection`. Si el tipo de elemento es una interfaz, el prefijo "I" del tipo de elemento se puede omitir. Por lo tanto, se puede llamar a una colección de elementos <xref:System.IDisposable> `DisposableCollection`.

 ✔️ considere la posibilidad de usar el prefijo "ReadOnly" en los nombres de las colecciones de solo lectura si se puede Agregar una colección grabable correspondiente o ya existe en el marco de trabajo.

 Por ejemplo, una colección de cadenas de solo lectura debe llamarse `ReadOnlyStringCollection`.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
