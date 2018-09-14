---
title: Diseño de parámetros
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea5311de8cef266af23b259d943568bfa95eaf72
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615081"
---
# <a name="parameter-design"></a>Diseño de parámetros
Esta sección proporciona instrucciones generales sobre el diseño de parámetro, incluidas secciones con instrucciones para la comprobación de argumentos. Además, debe hacer referencia a las directrices descritas en [parámetros nomenclatura](../../../docs/standard/design-guidelines/naming-parameters.md).  
  
 **✓ DO** usar el tipo de parámetro menos derivado que proporciona la funcionalidad requerida por el miembro.  
  
 Por ejemplo, suponga que desea diseñar un método que enumera una colección e imprime cada elemento en la consola. Este método debe tomar <xref:System.Collections.IEnumerable> como parámetro, no <xref:System.Collections.ArrayList> o <xref:System.Collections.IList>, por ejemplo.  
  
 **X DO NOT** utilizar parámetros reservados.  
  
 Si se necesitan más entradas para un miembro de alguna versión futura, se puede agregar una nueva sobrecarga.  
  
 **X DO NOT** públicamente ha expuesto métodos que toman punteros, matrices de punteros o matrices multidimensionales como parámetros.  
  
 Los punteros y matrices multidimensionales son relativamente difíciles de usar correctamente. En casi todos los casos, las API pueden modificarse para evitar realizar estos tipos como parámetros.  
  
 **✓ DO** colocar todos `out` seguir todos los valores de parámetros y `ref` parámetros (excluyendo matrices de parámetros), incluso si se produce una incoherencia en el orden entre las sobrecargas de los parámetros (consulte [miembro Sobrecarga](../../../docs/standard/design-guidelines/member-overloading.md)).  
  
 El `out` parámetros pueden verse como valores devueltos adicionales y agruparlos hace más fácil de entender que la firma del método.  
  
 **✓ DO** sea coherente en los nombres de parámetros al reemplazar los miembros o implementar miembros de interfaz.  
  
 Esto comunica mejor la relación entre los métodos.  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a>Elegir entre las enumeraciones y los parámetros booleanos  
 **✓ DO** utilice enumeraciones si un miembro podría tener dos o más parámetros booleanos.  
  
 **X DO NOT** utilice valores booleanos a menos que esté completamente seguro de que nunca será una necesidad de más de dos valores.  
  
 Las enumeraciones proporcionan algo de espacio para futuras además de valores, pero debe tener en cuenta todas las implicaciones de agregar valores a las enumeraciones, que se describen en [diseño de enumeraciones](../../../docs/standard/design-guidelines/enum.md).  
  
 **✓ CONSIDER** con valores booleanos para parámetros de constructor que son valores realmente de dos Estados y simplemente se utilizan para inicializar propiedades booleanas.  
  
### <a name="validating-arguments"></a>Validación de argumentos  
 **✓ DO** validar los argumentos pasados a miembros públicos, protegidos o implementados explícitamente. Producir <xref:System.ArgumentException?displayProperty=nameWithType>, o uno de sus subclases, si se produce un error en la validación.  
  
 Tenga en cuenta que la validación real no tiene necesariamente que se producen en el propio miembro público o protegido. Se puede producir en un nivel inferior de algunos rutina privado o interno. La cuestión principal es que todo el área de superficie que se expone a los usuarios finales las comprobaciones de los argumentos.  
  
 **✓ DO** throw <xref:System.ArgumentNullException> si se pasa un argumento nulo y el miembro no es compatible con los argumentos null.  
  
 **✓ DO** validar los parámetros enum.  
  
 No suponga argumentos enum estará en el intervalo definido por la enumeración. El CLR permite convertir cualquier valor entero a un valor de enumeración, incluso si el valor no está definido en la enumeración.  
  
 **X DO NOT** usar <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> para intervalo de enumeración comprueba.  
  
 **✓ DO** tenga en cuenta que los argumentos mutables pueden haber cambiado después de que se validaron.  
  
 Si el miembro es importante para la seguridad, se recomienda realizar una copia y, a continuación, validar y procesar el argumento.  
  
### <a name="parameter-passing"></a>Paso de parámetros  
 Desde la perspectiva de un diseñador de framework, hay tres grupos principales de parámetros: parámetros, por valor `ref` parámetros, y `out` parámetros.  
  
 Cuando se pasa un argumento mediante un parámetro por valor, el miembro recibe una copia del argumento real pasado. Si el argumento es un tipo de valor, se coloca una copia del argumento en la pila. Si el argumento es un tipo de referencia, se coloca una copia de la referencia en la pila. Lenguajes de CLR más populares, como C#, VB.NET y C++, de forma predeterminada para pasar parámetros por valor.  
  
 Cuando se pasa un argumento a través de un `ref` parámetro, el miembro recibe una referencia para el argumento real pasado. Si el argumento es un tipo de valor, una referencia al argumento se coloca en la pila. Si el argumento es un tipo de referencia, se coloca una referencia a la referencia en la pila. `Ref` parámetros se pueden usar para permitir que el miembro modificar los argumentos pasados por el llamador.  
  
 `Out` los parámetros son similares a `ref` parámetros, con algunas pequeñas diferencias. El parámetro se considera inicialmente sin asignar y no se puede leer en el cuerpo de miembro antes de asignarle algún valor. Además, el parámetro debe asignarse a algún valor antes de que devuelve el miembro.  
  
 **X AVOID** con `out` o `ref` parámetros.  
  
 Uso de `out` o `ref` parámetros requiere experiencia con punteros, saber la diferencia entre los tipos de valor y tipos de referencia y controlar métodos con varios valores devueltos. Además, la diferencia entre `out` y `ref` parámetros no se entiende ampliamente. Arquitectos de Framework diseñar para una audiencia general no deben esperar que los usuarios dominen el uso `out` o `ref` parámetros.  
  
 **X DO NOT** pasar tipos de referencia por referencia.  
  
 Hay algunas excepciones limitadas a la regla, como un método que se puede usar para intercambiar las referencias.  
  
### <a name="members-with-variable-number-of-parameters"></a>Miembros con un número Variable de parámetros  
 Los miembros que pueden tomar un número variable de argumentos se expresan proporcionando un parámetro de matriz. Por ejemplo, <xref:System.String> proporciona el método siguiente:  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 A continuación, puede llamar un usuario la <xref:System.String.Format%2A?displayProperty=nameWithType> método, como se indica a continuación:  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 Agregar la palabra clave params de C# para un parámetro de matriz cambia el parámetro a un parámetro de matriz de parámetros denominados y proporciona un acceso directo a la creación de una matriz temporal.  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 Esto permite al usuario que llame al método pasando los elementos de matriz directamente en la lista de argumentos.  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 Tenga en cuenta que se puede agregar la palabra clave params solo para el último parámetro en la lista de parámetros.  
  
 **✓ CONSIDER** agregar la palabra clave params a los parámetros de matriz si espera que los usuarios finales para pasar matrices con un número pequeño de elementos. Si se espera que una gran cantidad de elementos se pasará en común los escenarios, los usuarios probablemente no pasará estos elementos insertados de todos modos y, por lo que la palabra clave params no es necesaria.  
  
 **X AVOID** usar matrices de parámetros si el llamador casi siempre tendrá la entrada ya en una matriz.  
  
 Por ejemplo, los miembros con los parámetros de matriz de bytes casi nunca se llamaría pasando bytes individuales. Por este motivo, los parámetros de matriz de bytes en .NET Framework no use la palabra clave params.  
  
 **X DO NOT** usar matrices de parámetros si se modifica la matriz por el miembro que toma el parámetro de matriz de parámetros.  
  
 Por el hecho de que muchos compiladores convierten los argumentos para el miembro en una matriz temporal en el sitio de llamada, la matriz podría ser un objeto temporal y, por lo tanto, se perderán las modificaciones en la matriz.  
  
 **✓ CONSIDER** mediante la palabra clave params en una sobrecarga simple, aun cuando una sobrecarga más compleja no pudo usar.  
  
 Pregúntese si los usuarios Valoraremos con la matriz de parámetros en una sobrecarga, aunque no en todas las sobrecargas.  
  
 **✓ DO** intenta reorganizar los parámetros para que sea posible utilizar la palabra clave params.  
  
 **✓ CONSIDER** proporcionar sobrecargas especiales y las rutas de código para las llamadas con un número pequeño de argumentos en las API de rendimiento es sumamente importante.  
  
 Esto hace que sea posible para evitar la creación de objetos de matriz cuando se llama a la API con un pequeño número de argumentos. Formar los nombres de los parámetros tomando una forma singular del parámetro de matriz y agregar un sufijo numérico.  
  
 Solo debe hacerlo si va a la ruta de acceso de código completo de casos especiales, no basta con crear una matriz y llame al método más general.  
  
 **✓ DO** tenga en cuenta que null podría pasarse como un argumento de matriz de parámetros.  
  
 Debe validar que la matriz no es null antes del procesamiento.  
  
 **X DO NOT** utilizar el `varargs` métodos, también conocidas como los puntos suspensivos.  
  
 Algunos lenguajes CLR, como C++, admiten una convención alternativa para pasar las listas de parámetros de variable llamadas `varargs` métodos. No debe utilizarse la convención en marcos, porque no es conforme a CLS.  
  
### <a name="pointer-parameters"></a>Parámetros de puntero  
 En general, los punteros no deben aparecer en el área de superficie público de un marco de código administrado bien diseñada. La mayoría de los casos, se deben encapsular punteros. Sin embargo, en algunos casos, los punteros son necesarios por motivos de interoperabilidad y el uso de punteros en estos casos es adecuado.  
  
 **✓ DO** proporcionan una alternativa para cualquier miembro que tome un argumento de puntero, como punteros no son conformes a CLS.  
  
 **X AVOID** realizar comprobaciones de los argumentos de puntero de argumento costoso.  
  
 **✓ DO** siga las convenciones comunes relacionadas con el puntero al diseñar los miembros con punteros.  
  
 Por ejemplo, no hay ninguna necesidad de pasar el índice de inicio, porque se puede usar aritmética de puntero simple para lograr el mismo resultado.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
