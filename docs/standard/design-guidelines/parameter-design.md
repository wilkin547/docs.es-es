---
title: Diseño de parámetros
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: KrzysztofCwalina
ms.openlocfilehash: 93554594b49b742a6a5e8461b6b16046701ec07c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347849"
---
# <a name="parameter-design"></a>Diseño de parámetros

En esta sección se proporcionan instrucciones generales sobre el diseño de parámetros, incluidas las secciones con instrucciones para comprobar los argumentos. Además, debe consultar las directrices descritas en nomenclatura de [parámetros](../../../docs/standard/design-guidelines/naming-parameters.md).  
  
 **✓ DO** usar el tipo de parámetro menos derivado que proporciona la funcionalidad requerida por el miembro.  
  
 Por ejemplo, suponga que desea diseñar un método que enumera una colección e imprime cada elemento en la consola. Este tipo de método debe tomar <xref:System.Collections.IEnumerable> como parámetro, no <xref:System.Collections.ArrayList> ni <xref:System.Collections.IList>, por ejemplo.  
  
 **X DO NOT** utilizar parámetros reservados.  
  
 Si se necesita más entrada a un miembro en alguna versión futura, se puede Agregar una nueva sobrecarga.  
  
 **X DO NOT** públicamente ha expuesto métodos que toman punteros, matrices de punteros o matrices multidimensionales como parámetros.  
  
 Los punteros y las matrices multidimensionales son relativamente difíciles de usar correctamente. En casi todos los casos, las API se pueden rediseñar para evitar que estos tipos sean parámetros.  
  
 **✓ DO** colocar todos `out` seguir todos los valores de parámetros y `ref` parámetros (excluyendo matrices de parámetros), incluso si se produce una incoherencia en el orden entre las sobrecargas de los parámetros (consulte [miembro Sobrecarga](../../../docs/standard/design-guidelines/member-overloading.md)).  
  
 Los parámetros `out` se pueden ver como valores devueltos adicionales y, al agruparlos, la firma del método resulta más fácil de entender.  
  
 **✓ DO** sea coherente en los nombres de parámetros al reemplazar los miembros o implementar miembros de interfaz.  
  
 Esto comunica mejor la relación entre los métodos.  
  
### <a name="choose-between-enum-and-boolean-parameters"></a>Elección entre parámetros booleanos y de enumeración  
 **✓ DO** utilice enumeraciones si un miembro podría tener dos o más parámetros booleanos.  
  
 **X DO NOT** utilice valores booleanos a menos que esté completamente seguro de que nunca será una necesidad de más de dos valores.  
  
 Las enumeraciones ofrecen algún espacio para la adición futura de valores, pero debe tener en cuenta todas las implicaciones de agregar valores a las enumeraciones, que se describen en el [diseño de enumeraciones](../../../docs/standard/design-guidelines/enum.md).  
  
 **✓ CONSIDER** con valores booleanos para parámetros de constructor que son valores realmente de dos Estados y simplemente se utilizan para inicializar propiedades booleanas.  
  
### <a name="validate-arguments"></a>Validar argumentos  
 **✓ DO** validar los argumentos pasados a miembros públicos, protegidos o implementados explícitamente. Produce <xref:System.ArgumentException?displayProperty=nameWithType>, o una de sus subclases, si se produce un error en la validación.  
  
 Tenga en cuenta que no es necesario que la validación real se produzca en el propio miembro público o protegido. Podría producirse en un nivel inferior en algunas rutinas internas o privadas. El punto principal es que todo el área expuesta que se expone a los usuarios finales comprueba los argumentos.  
  
 **✓ DO** throw <xref:System.ArgumentNullException> si se pasa un argumento nulo y el miembro no es compatible con los argumentos null.  
  
 **✓ DO** validar los parámetros enum.  
  
 No asuma que los argumentos de enumeración estarán en el intervalo definido por la enumeración. CLR permite convertir cualquier valor entero en un valor de enumeración incluso si el valor no está definido en la enumeración.  
  
 **X DO NOT** usar <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> para intervalo de enumeración comprueba.  
  
 **✓ DO** tenga en cuenta que los argumentos mutables pueden haber cambiado después de que se validaron.  
  
 Si el miembro es sensible a la seguridad, se recomienda hacer una copia y, a continuación, validar y procesar el argumento.  
  
### <a name="pass-parameters"></a>Paso de parámetros  
 Desde la perspectiva de un diseñador de Marcos, hay tres grupos principales de parámetros: por valor, parámetros `ref` y parámetros de `out`.  
  
 Cuando un argumento se pasa a través de un parámetro por valor, el miembro recibe una copia del argumento real pasado. Si el argumento es un tipo de valor, se coloca una copia del argumento en la pila. Si el argumento es un tipo de referencia, se coloca una copia de la referencia en la pila. Los lenguajes CLR más populares, C#como, Visual Basic y C++, de forma predeterminada pasan los parámetros por valor.  
  
 Cuando un argumento se pasa a través de un parámetro `ref`, el miembro recibe una referencia al argumento real pasado. Si el argumento es un tipo de valor, se coloca una referencia al argumento en la pila. Si el argumento es un tipo de referencia, se coloca en la pila una referencia a la referencia. `Ref` parámetros se pueden usar para permitir que el miembro modifique los argumentos pasados por el autor de la llamada.  
  
 `Out` parámetros son similares a los parámetros de `ref`, con algunas pequeñas diferencias. El parámetro se considera inicialmente sin asignar y no se puede leer en el cuerpo del miembro antes de que se le asigne algún valor. Además, el parámetro tiene que tener asignado algún valor antes de que el miembro devuelva.  
  
 **X AVOID** con `out` o `ref` parámetros.  
  
 El uso de los parámetros `out` o `ref` requiere experiencia con punteros, comprender cómo difieren los tipos de valor y de referencia, y cómo controlar métodos con varios valores devueltos. Además, la diferencia entre los parámetros `out` y `ref` no se comprende ampliamente. Los arquitectos de Framework que diseñan para una audiencia general no deben esperar que los usuarios dominen el trabajo con `out` o `ref` parámetros.  
  
 **X DO NOT** pasar tipos de referencia por referencia.  
  
 Hay algunas excepciones limitadas a la regla, como un método que se puede utilizar para intercambiar referencias.  
  
### <a name="members-with-variable-number-of-parameters"></a>Miembros con número variable de parámetros  
 Los miembros que pueden tomar un número variable de argumentos se expresan proporcionando un parámetro de matriz. Por ejemplo, <xref:System.String> proporciona el método siguiente:  
  
```csharp  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 Después, un usuario puede llamar al método <xref:System.String.Format%2A?displayProperty=nameWithType>, como se indica a continuación:  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 Al agregar C# la palabra clave params a un parámetro de matriz, se cambia el parámetro a un parámetro de matriz denominado params y se proporciona un acceso directo a la creación de una matriz temporal.  
  
```csharp  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 De este modo, el usuario puede llamar al método pasando los elementos de la matriz directamente en la lista de argumentos.  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 Tenga en cuenta que la palabra clave params solo se puede Agregar al último parámetro de la lista de parámetros.  
  
 **✓ CONSIDER** agregar la palabra clave params a los parámetros de matriz si espera que los usuarios finales para pasar matrices con un número pequeño de elementos. Si se espera que se pasen muchos elementos en escenarios comunes, es probable que los usuarios no pasen estos elementos en línea de todas formas, por lo que no es necesario usar la palabra clave params.  
  
 **X AVOID** usar matrices de parámetros si el llamador casi siempre tendrá la entrada ya en una matriz.  
  
 Por ejemplo, nunca se llamaría a los miembros con parámetros de matriz de bytes pasando bytes individuales. Por esta razón, los parámetros de matriz de bytes del .NET Framework no utilizan la palabra clave params.  
  
 **X DO NOT** usar matrices de parámetros si se modifica la matriz por el miembro que toma el parámetro de matriz de parámetros.  
  
 Debido al hecho de que muchos compiladores convierten los argumentos en el miembro en una matriz temporal en el sitio de llamada, la matriz puede ser un objeto temporal y, por tanto, se perderán todas las modificaciones de la matriz.  
  
 **✓ CONSIDER** mediante la palabra clave params en una sobrecarga simple, aun cuando una sobrecarga más compleja no pudo usar.  
  
 Pregúntese si los usuarios van a tener la matriz params en una sobrecarga aunque no estuvieran en todas las sobrecargas.  
  
 **✓ DO** intenta reorganizar los parámetros para que sea posible utilizar la palabra clave params.  
  
 **✓ CONSIDER** proporcionar sobrecargas especiales y las rutas de código para las llamadas con un número pequeño de argumentos en las API de rendimiento es sumamente importante.  
  
 Esto permite evitar la creación de objetos de matriz cuando se llama a la API con un pequeño número de argumentos. Formar los nombres de los parámetros tomando una forma singular del parámetro de la matriz y agregando un sufijo numérico.  
  
 Solo debe hacerlo si va a utilizar la ruta de acceso a todo el código, no solo crea una matriz y llama al método más general.  
  
 **✓ DO** tenga en cuenta que null podría pasarse como un argumento de matriz de parámetros.  
  
 Debe validar que la matriz no sea NULL antes del procesamiento.  
  
 **X DO NOT** utilizar el `varargs` métodos, también conocidas como los puntos suspensivos.  
  
 Algunos lenguajes CLR, como C++, admiten una Convención alternativa para pasar listas de parámetros de variables llamadas `varargs` métodos. La Convención no debe usarse en marcos de trabajo, ya que no es conforme a CLS.  
  
### <a name="pointer-parameters"></a>Parámetros de puntero  
 En general, los punteros no deberían aparecer en el área expuesta pública de un marco de código administrado bien diseñado. La mayoría de las veces, se deben encapsular los punteros. Sin embargo, en algunos casos, se requieren punteros por motivos de interoperabilidad y el uso de punteros en estos casos es adecuado.  
  
 **✓ DO** proporcionan una alternativa para cualquier miembro que tome un argumento de puntero, como punteros no son conformes a CLS.  
  
 **X AVOID** realizar comprobaciones de los argumentos de puntero de argumento costoso.  
  
 **✓ DO** siga las convenciones comunes relacionadas con el puntero al diseñar los miembros con punteros.  
  
 Por ejemplo, no es necesario pasar el índice de inicio, ya que se puede usar una aritmética de puntero simple para lograr el mismo resultado.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
