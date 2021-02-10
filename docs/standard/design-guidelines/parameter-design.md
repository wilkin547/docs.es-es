---
description: 'Más información acerca de: Diseño de parámetros'
title: Diseño de parámetros
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
ms.openlocfilehash: 9663ef8146054985374fdb3e2974fcd996fd1402
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731830"
---
# <a name="parameter-design"></a>Diseño de parámetros

En esta sección se proporcionan instrucciones generales sobre el diseño de parámetros, incluidas las secciones con instrucciones para comprobar los argumentos. Además, debe consultar las instrucciones descritas en [Asignación de nombres a parámetros](naming-parameters.md).

 ✔️ USE el tipo de parámetro menos derivado que proporcione la funcionalidad necesaria para el miembro.

 Por ejemplo, suponga que desea diseñar un método que enumere una colección e imprima cada elemento en la consola. Este tipo de método debe tomar <xref:System.Collections.IEnumerable> como parámetro, no <xref:System.Collections.ArrayList> ni <xref:System.Collections.IList>, por ejemplo.

 ❌ NO use parámetros reservados.

 Si se necesita más información de un miembro en alguna versión futura, se puede agregar una nueva sobrecarga.

 ❌ NO tenga métodos expuestos públicamente que tomen punteros, matrices de punteros o matrices multidimensionales como parámetros.

 Los punteros y las matrices multidimensionales son relativamente difíciles de usar de forma correcta. En casi todos los casos, las API se pueden rediseñar para evitar que estos tipos se tomen como parámetros.

 ✔️ COLOQUE todos los parámetros `out` que siguen a todos los parámetros `ref` y por valor (excepto las matrices de parámetros), incluso si se produce una incoherencia en el orden de los parámetros entre sobrecargas (consulte [Sobrecarga de miembro](member-overloading.md)).

 Los parámetros `out` se pueden ver como valores devueltos adicionales y, al agruparlos, la firma del método resulta más fácil de entender.

 ✔️ SEA coherente a la hora de asignar nombres cuando se invaliden los miembros o se implementen los miembros de interfaz.

 Esto hace que se comunique mejor la relación entre los métodos.

### <a name="choosing-between-enum-and-boolean-parameters"></a>Elección entre parámetros booleanos y de enumeración  

 ✔️ USE enumeraciones si, de lo contrario, un miembro tendría dos o más parámetros booleanos.

 ❌ NO use valores booleanos a menos que esté absolutamente seguro de que nunca se necesitarán más de dos valores.

 Las enumeraciones le ofrecen espacio para la adición futura de valores, pero debe tener en cuenta todas las implicaciones de agregar valores a las enumeraciones, que se describen en [Diseño de enumeraciones](enum.md).

 ✔️ CONSIDERE la posibilidad de usar valores booleanos para los parámetros del constructor que sean en realidad valores de dos estados y se utilicen simplemente para inicializar las propiedades booleanas.

### <a name="validating-arguments"></a>Validación de argumentos

 ✔️ VALIDE los argumentos pasados a miembros públicos, protegidos o implementados explícitamente. Inicie <xref:System.ArgumentException?displayProperty=nameWithType> o una de sus subclases si se produce un error en la validación.

 Tenga en cuenta que no es necesario que la validación real se produzca en el propio miembro público o protegido. Podría producirse en un nivel inferior en algunas rutinas internas o privadas. Lo más importante es que todo el área expuesta que se expone a los usuarios finales comprueba los argumentos.

 ✔️ INICIE <xref:System.ArgumentNullException> si se pasa un argumento NULL y el miembro no admite argumentos NULL.

 ✔️ VALIDE los parámetros de enumeración.

 No suponga que los argumentos de enumeración estarán en el intervalo definido por la enumeración. CLR permite convertir cualquier valor entero en un valor de enumeración incluso si el valor no está definido en la enumeración.

 ❌ NO use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> para las comprobaciones de intervalos de enumeración.

 ✔️ TENGA en cuenta que los argumentos mutables podrían haber cambiado una vez validados.

 Si el miembro es sensible desde el punto de vista de la seguridad, se recomienda que realice una copia y, a continuación, valide y procese el argumento.

### <a name="parameter-passing"></a>Paso de parámetros

 Desde la perspectiva de un diseñador de marcos, hay tres grupos principales de parámetros: por valor, `ref` y `out`.

 Cuando un argumento se pasa a través de un parámetro por valor, el miembro recibe una copia del argumento real pasado. Si el argumento es un tipo de valor, se coloca una copia del argumento en la pila. Si el argumento es un tipo de referencia, se coloca una copia de la referencia en la pila. Los lenguajes CLR más populares, como C# , VB.NET y C++, usan el paso de parámetros por valor como valor predeterminado.

 Cuando un argumento se pasa a través de un parámetro `ref`, el miembro recibe una referencia al argumento real pasado. Si el argumento es un tipo de valor, se coloca una referencia al argumento en la pila. Si el argumento es un tipo de referencia, se coloca una referencia a la referencia en la pila. Los parámetros `Ref` se pueden usar para permitir que el miembro modifique los argumentos pasados por el llamador.

 Los parámetros `Out` son similares a los parámetros `ref`, con algunas pequeñas diferencias. Se considera inicialmente que el parámetro está sin asignar y no se puede leer en el cuerpo del miembro antes de que se le asigne algún valor. Además, debe asignarse algún valor al parámetro antes de que vuelva el miembro.

 ❌ EVITE usar los parámetros `out` o `ref`.

 Para usar los parámetros `out` o `ref` es necesario tener experiencia con punteros, saber la diferencia entre los tipos de referencia y los tipos de valor, y controlar métodos con varios valores devueltos. Además, no se suele saber qué diferencia hay entre los parámetros `out` y `ref`. Los arquitectos de marcos que diseñan para una audiencia general no deben esperar que los usuarios dominen el trabajo con los parámetros `out` o `ref`.

 ❌ NO pase tipos de referencia por referencia.

 Hay algunas excepciones limitadas a la regla, como un método que se puede utilizar para intercambiar referencias.

### <a name="members-with-variable-number-of-parameters"></a>Miembros con un número variable de parámetros

 Los miembros que pueden tomar un número variable de argumentos se expresan proporcionando un parámetro de matriz. Por ejemplo, <xref:System.String> proporciona el método siguiente:

```csharp
public class String {
    public static string Format(string format, object[] parameters);
}
```

 A continuación, un usuario puede llamar al método <xref:System.String.Format%2A?displayProperty=nameWithType>, como se indica a continuación:

 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`

 Con la incorporación de la palabra clave params de C# a un parámetro de matriz, el parámetro cambia a un parámetro de matriz llamado params y se proporciona un acceso directo a la creación de una matriz temporal.

```csharp
public class String {
    public static string Format(string format, params object[] parameters);
}
```

 De este modo, el usuario puede llamar al método pasando los elementos de matriz directamente a la lista de argumentos.

 `String.Format("File {0} not found in {1}",filename,directory);`

 Tenga en cuenta que la palabra clave params solo se puede agregar al último parámetro de la lista de parámetros.

 ✔️ CONSIDERE la posibilidad de agregar la palabra clave params a los parámetros de matriz si espera que los usuarios finales pasen matrices con un pequeño número de elementos. Si se espera que se pasen muchos elementos a escenarios comunes, es probable que los usuarios no pasen estos elementos en línea de todas formas, por lo que no es necesaria la palabra clave params.

 ❌ EVITE usar matrices params si el llamador ya tuviera casi siempre la entrada en una matriz.

 Por ejemplo, nunca se llamaría a los miembros con parámetros de matriz de bytes pasando bytes individuales. Es por ello que los parámetros de matriz de bytes de .NET Framework no usan la palabra clave params.

 ❌ NO use matrices params si el miembro que toma el parámetro de matriz params modifica la matriz.

 Dado que muchos compiladores convierten los argumentos del miembro en una matriz temporal en el sitio de llamada, la matriz podría ser un objeto temporal y, por tanto, se perderán todas las modificaciones en la matriz.

 ✔️ CONSIDERE la posibilidad de usar la palabra clave params en una sobrecarga simple, incluso si una sobrecarga más compleja no pudiera utilizarla.

 Pregúntese si los usuarios valorarían el hecho de tener la matriz params en una sobrecarga incluso si no estuviera en todas las sobrecargas.

 ✔️ INTENTE ordenar los parámetros para poder usar la palabra clave params.

 ✔️ CONSIDERE la posibilidad de proporcionar sobrecargas y rutas de acceso al código especiales para las llamadas con un pequeño número de argumentos en las API que requieran un rendimiento muy alto.

 Esto permite evitar la creación de objetos de matriz cuando se llama a la API con un pequeño número de argumentos. Forme los nombres de los parámetros tomando una forma singular del parámetro de matriz y agregando un sufijo numérico.

 Solo debe hacerlo si va a marcar como caso especial toda la ruta de acceso al código, no solo crear una matriz y llamar al método más general.

 ✔️ TENGA EN CUENTA que NULL podría pasarse como un argumento de matriz params.

 Debe validar que la matriz no sea NULL antes del procesamiento.

 ❌ NO use los métodos`varargs`, también conocidos como puntos suspensivos.

 Algunos lenguajes CLR, como C++, admiten una convención alternativa para pasar listas de parámetros variables llamadas métodos `varargs`. La convención no debe usarse en marcos, ya que no es conforme a CLS.

### <a name="pointer-parameters"></a>Parámetros de puntero

 En general, los punteros no deberían aparecer en el área expuesta pública de un marco de código administrado bien diseñado. La mayoría de las veces, se deben encapsular los punteros. Sin embargo, en algunos casos, se requieren punteros por motivos de interoperabilidad y, en estos casos, su uso es adecuado.

 ✔️ PROPORCIONE una alternativa para cualquier miembro que tome un argumento de puntero, ya que los punteros no son conformes a CLS.

 ❌ EVITE realizar una comprobación costosa de los argumentos de puntero.

 ✔️ SIGA las convenciones habituales relacionadas con el puntero al diseñar miembros con punteros.

 Por ejemplo, no es necesario pasar el índice de inicio, ya que se puede usar una aritmética de puntero simple para lograr el mismo resultado.

 *Portions &copy; 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](member.md)
- [Instrucciones de diseño de .NET Framework](index.md)
