---
title: "Dise&#241;o de par&#225;metros | Microsoft Docs"
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
helpviewer_keywords: 
  - "instrucciones de diseño de miembros [.NET Framework], parámetros"
  - "miembros [.NET Framework], parámetros"
  - "nombres [.NET Framework], parámetros"
  - "parámetros, instrucciones de diseño"
  - "parámetros reservados"
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Dise&#241;o de par&#225;metros
Esta sección proporciona instrucciones generales sobre el diseño de parámetro, incluidas las secciones con instrucciones para comprobar argumentos. Además, debe consultar las instrucciones descritas en [Nomenclatura de parámetros](../../../docs/standard/design-guidelines/naming-parameters.md).  
  
 **✓ hacer** usar el tipo de parámetro menos derivado que proporciona la funcionalidad requerida por el miembro.  
  
 Por ejemplo, suponga que desea diseñar un método que enumera una colección e imprime cada elemento en la consola. Este método debe tomar <xref:System.Collections.IEnumerable> como parámetro, no <xref:System.Collections.ArrayList> o <xref:System.Collections.IList>, por ejemplo.  
  
 **X no** utilizar parámetros reservados.  
  
 Si se necesitan más entradas a un miembro de alguna versión futura, se puede agregar una nueva sobrecarga.  
  
 **X no** públicamente ha expuesto métodos que toman punteros, matrices de punteros o matrices multidimensionales como parámetros.  
  
 Los punteros y matrices multidimensionales son relativamente difíciles de usar correctamente. En casi todos los casos, se pueden volver a diseñar API para evitar realizar estos tipos como parámetros.  
  
 **✓ hacer** colocar todos los `out` parámetros después de todo el valor y `ref` parámetros \(excluyendo matrices de parámetros\), incluso si se produce una incoherencia en el orden entre las sobrecargas de los parámetros \(consulte [Sobrecarga de miembro](../../../docs/standard/design-guidelines/member-overloading.md)\).  
  
 El `out` parámetros pueden verse como valores devueltos adicionales y agrupándolas hace que la firma del método más fácil de entender.  
  
 **✓ hacer** ser coherente de nomenclatura de parámetros al reemplazar los miembros o implementar miembros de interfaz.  
  
 Esto comunica mejor la relación entre los métodos.  
  
### Elegir entre Enum y parámetros booleanos  
 **✓ hacer** utilice enumeraciones si un miembro tendría dos o más parámetros booleanos.  
  
 **X no** utilice valores booleanos a menos que esté totalmente seguro de que nunca será una necesidad de más de dos valores.  
  
 Las enumeraciones dejan espacio para futuras además de valores, pero tenga en cuenta todas las implicaciones de agregar valores a las enumeraciones, que se describen en [Diseño de enumeraciones](../../../docs/standard/design-guidelines/enum.md).  
  
 **✓ considere** con valores booleanos para parámetros de constructor que son realmente dos Estados, valores y simplemente se utilizan para inicializar las propiedades booleanas.  
  
### Validación de argumentos  
 **✓ hacer** Validar argumentos pasados a miembros públicos, protegidos o implementados explícitamente. Iniciar <xref:System.ArgumentException?displayProperty=fullName>, o una de sus subclases, si falla la validación.  
  
 Tenga en cuenta que la validación no tiene necesariamente que ocurra en el propio miembro público o protegido. Se puede producir en un nivel inferior de algunos rutina privado o interno. La cuestión principal es que toda la superficie que se expone a los usuarios finales las comprobaciones de los argumentos.  
  
 **✓ hacer** throw <xref:System.ArgumentNullException> Si se pasa un argumento null y el miembro no admite los argumentos nulos.  
  
 **✓ hacer** validar parámetros de enumeración.  
  
 No suponga argumentos enum estará en el intervalo definido por la enumeración. CLR permite convertir cualquier valor entero a un valor de enumeración, incluso si el valor no está definido en la enumeración.  
  
 **X no** use <xref:System.Enum.IsDefined%2A?displayProperty=fullName> para intervalo de enumeración comprueba.  
  
 **✓ hacer** tenga en cuenta que los argumentos mutables pueden haber cambiado después de haber sido validados.  
  
 Si el miembro es importante para la seguridad, se recomienda hacer una copia y, a continuación, validar y procesar el argumento.  
  
### Paso de parámetros  
 Desde la perspectiva de un diseñador de framework, hay tres grupos principales de parámetros: parámetros, por valor `ref` parámetros, y `out` parámetros.  
  
 Cuando se pasa un argumento a través de un parámetro por valor, el miembro recibe una copia del argumento real pasado. Si el argumento es un tipo de valor, se coloca una copia del argumento en la pila. Si el argumento es un tipo de referencia, se coloca una copia de la referencia en la pila. Lenguajes de CLR más populares, como C\#, VB.NET y C\+\+, de forma predeterminada para pasar parámetros por valor.  
  
 Cuando se pasa un argumento a través de un `ref` parámetro, el miembro recibe una referencia al argumento real pasado. Si el argumento es un tipo de valor, una referencia al argumento se coloca en la pila. Si el argumento es un tipo de referencia, una referencia a la referencia se coloca en la pila.`Ref` parámetros pueden utilizarse para permitir que el miembro modificar los argumentos pasados por el llamador.  
  
 `Out` parámetros son similares a `ref` parámetros, con algunas pequeñas diferencias. El parámetro se considera inicialmente no asignado y no se puede leer el cuerpo del miembro antes de que se le asigna un valor. Además, el parámetro debe asignarse a algún valor antes de que el miembro devuelve.  
  
 **Evitar X** con `out` o `ref` parámetros.  
  
 Mediante `out` o `ref` parámetros es necesario tener experiencia con punteros, saber la diferencia entre los tipos de valor y tipos de referencia y controlar métodos con varios valores devueltos. Además, la diferencia entre `out` y `ref` parámetros no se suele saber. Arquitectos de Framework diseñar para una audiencia general no deben esperar que los usuarios dominen el uso con `out` o `ref` parámetros.  
  
 **X no** pasar tipos de referencia por referencia.  
  
 Hay algunas excepciones a la regla, como un método que puede utilizar para intercambiar referencias limitadas.  
  
### Miembros con un número Variable de parámetros  
 Los miembros que pueden tomar un número variable de argumentos se expresan proporcionando un parámetro de matriz. Por ejemplo, <xref:System.String> proporciona el método siguiente:  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 A continuación, puede llamar un usuario la <xref:System.String.Format%2A?displayProperty=fullName> método como sigue:  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 Agregar la palabra clave params de C\# para un parámetro de matriz cambia el parámetro a un parámetro de matriz de parámetros denominados y proporciona un acceso directo a la creación de una matriz temporal.  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 Esto permite al usuario que llame al método pasando los elementos de matriz directamente en la lista de argumentos.  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 Tenga en cuenta que la palabra clave params puede agregarse sólo para el último parámetro en la lista de parámetros.  
  
 **✓ considere** agregando la palabra clave params a los parámetros de la matriz si espera que los usuarios finales para pasar matrices con un número pequeño de elementos. Si se espera que una gran cantidad de elementos se pasará en común los escenarios, los usuarios probablemente no pasará alineado de estos elementos de todos modos y, por lo que la palabra clave params no es necesaria.  
  
 **Evitar X** con matrices de parámetros si el llamador casi siempre tendrá la entrada ya en una matriz.  
  
 Por ejemplo, los miembros con parámetros de matriz de bytes casi nunca se llamaría pasando bytes individuales. Por esta razón, los parámetros de matriz de bytes en .NET Framework no utilizan la palabra clave params.  
  
 **X no** utilice matrices de parámetros si el miembro que toma el parámetro de matriz de parámetros modifica la matriz.  
  
 Debido al hecho de que muchos compiladores activar los argumentos al miembro en una matriz temporal en el sitio de llamada, la matriz puede ser un objeto temporal y, por lo tanto, se perderán las modificaciones a la matriz.  
  
 **✓, considere la posibilidad de** mediante la palabra clave params en una sobrecarga simple, aun cuando una sobrecarga más compleja no pudo usar.  
  
 Pregúntese si los usuarios valoraría con la matriz de parámetros en una sobrecarga, aunque no en todas las sobrecargas.  
  
 **✓ hacer** intenta reorganizar los parámetros para que sea posible utilizar la palabra clave params.  
  
 **✓ considere** proporcionar sobrecargas especiales y rutas de acceso de código para las llamadas con un pequeño número de argumentos de la API de rendimiento es sumamente importante.  
  
 Esto permite evitar la creación de objetos de la matriz cuando se llama a la API con un número pequeño de argumentos. Los nombres de los parámetros de formulario tomando una forma singular del parámetro de matriz y agrega un sufijo numérico.  
  
 Sólo debe hacerlo si va a la ruta de acceso de código completo de casos especiales, no basta con crear una matriz y llame al método más general.  
  
 **✓ hacer** tenga en cuenta que null podría pasarse como un argumento de matriz de parámetros.  
  
 Debe validar que la matriz no es null antes del procesamiento.  
  
 **X no** utilizar el `varargs` métodos, también conocidas como los puntos suspensivos.  
  
 Algunos lenguajes CLR, como C\+\+, admiten una convención alternativa para pasar las listas de parámetros de variable denominadas `varargs` métodos. La convención no debe usarse en marcos, porque no es compatible con CLS.  
  
### Parámetros de puntero  
 En general, los punteros no deben aparecer en el área de superficie pública de un marco de código administrado bien diseñada. La mayoría de los casos, se deben encapsular punteros. Sin embargo, en algunos casos, los punteros son necesarios por motivos de interoperabilidad y el uso de punteros en estos casos es adecuado.  
  
 **✓ hacer** proporcionan una alternativa para cualquier miembro que tome un argumento de puntero, ya que los punteros no son conformes a CLS.  
  
 **Evitar X** realizar costosa argumento comprobaciones de los argumentos de puntero.  
  
 **✓ hacer** siga convenciones comunes relacionados con el puntero cuando diseñe miembros con punteros.  
  
 Por ejemplo, no hay para pasar el índice de inicio, como la aritmética con punteros simple puede utilizarse para lograr el mismo resultado.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)