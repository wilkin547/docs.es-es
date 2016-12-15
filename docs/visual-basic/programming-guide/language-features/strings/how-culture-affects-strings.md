---
title: "C&#243;mo afecta la referencia cultural a las cadenas en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "configuración regional, efecto en cadenas"
  - "cadenas [Visual Basic], dependencia de la configuración regional"
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo afecta la referencia cultural a las cadenas en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

En esta página de ayuda se describe cómo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] usa la información de referencia cultural para realizar conversiones y comparaciones de cadenas.  
  
## Cuándo utilizar las cadenas específicas de referencia cultural  
 Normalmente, debe utilizar cadenas específicas de referencia cultural para todos los datos que se presentan a y se leen de los usuarios y utilizar cadenas independientes de la referencia cultural para los datos internos de la aplicación.  
  
 Por ejemplo, si la aplicación pide a los usuarios que escriban una fecha como una cadena, debe esperar que los usuarios adopten el formato de las cadenas correspondiente a su referencia cultural y debe convertir la cadena de manera adecuada.  Si a continuación la aplicación presenta esta fecha en su interfaz de usuario, debe presentarla en la referencia cultural del usuario.  
  
 Sin embargo, si la aplicación carga la fecha en un servidor central, debe aplicar a la cadena el formato correspondiente a una referencia cultural específica, para evitar la confusión entre formatos de fecha potencialmente diferentes.  
  
## Funciones que tienen en cuenta la referencia cultural  
 Todas las funciones de conversión de cadenas de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] \(excepto las funciones `Str` y `Val`\) usan la información de referencia cultural de la aplicación para asegurarse de que las conversiones y comparaciones resultan adecuadas para la referencia cultural del usuario de la aplicación.  
  
 La clave para utilizar correctamente las funciones de conversión de cadenas en aplicaciones que se ejecutan en equipos con configuraciones de referencia cultural diferentes consiste en comprender qué funciones utilizan una configuración de referencia cultural específica y cuáles utilizan la configuración de referencia cultural actual.  Observe que la configuración de la referencia cultural de la aplicación, de manera predeterminada, se hereda de la configuración de la referencia cultural del sistema operativo.  Para obtener más información, vea <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A> y [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Las funciones `Str` \(convierte números a cadenas\) y `Val` \(convierte cadenas a números\) no utilizan la información de referencia cultural de la aplicación cuando convierten entre cadenas y números.  De hecho, solo reconocen el punto \(.\) como separador decimal válido.  Los elementos análogos de estas funciones que sí tienen en cuenta la referencia cultural son:  
  
-   **Conversiones que utilizan la referencia cultural actual.** Las funciones `CStr` y `Format` convierten un número en una cadena y las funciones `CDbl` y `CInt` convierten una cadena en un número.  
  
-   **Conversiones que utilizan una referencia cultural específica.** Cada objeto de número dispone de un método `ToString(IFormatProvider)` que convierte un número en una cadena y un método `Parse(String, IFormatProvider)` que convierte una cadena en un número.  Por ejemplo, el tipo `Double` proporciona los métodos <xref:System.Double.ToString%28System.IFormatProvider%29> y <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29>.  
  
 Para obtener más información, vea <xref:Microsoft.VisualBasic.Conversion.Str%2A> y <xref:Microsoft.VisualBasic.Conversion.Val%2A>.  
  
## Utilizar una referencia cultural concreta  
 Supongamos que desarrolla una aplicación que envía una fecha \(con formato de cadena\) a un servicio Web.  En este caso, la aplicación debe utilizar una referencia cultural concreta para la conversión de cadenas.  Para explicarlo, supongamos cuál es el resultado de utilizar el método <xref:System.DateTime.ToString> de la fecha: Si la aplicación utiliza este método para aplicar formato a la fecha 4 de julio de 2005, devuelve "7\/4\/2005 12:00:00 AM" cuando se ejecuta con la referencia cultural de inglés de Estados Unidos \(en\-US\) o "04.07.2005 00:00:00" cuando se ejecuta con la referencia cultura de alemán \(de\-DE\).  
  
 Cuando necesite realizar una conversión de cadenas en un formato de referencia cultural específico, debe usar la clase `CultureInfo` integrada en [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].  Puede crear un nuevo objeto `CultureInfo` para una referencia cultural concreta pasando el nombre de la referencia cultural al constructor <xref:System.Globalization.CultureInfo.%23ctor%2A>.  Los nombres de referencia cultural compatibles se muestran en la página de ayuda de la clase <xref:System.Globalization.CultureInfo>.  
  
 También puede obtener una instancia de la *referencia cultural de todos los idiomas* de la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  La referencia cultural de todos los idiomas se basa en la referencia cultural inglesa, pero hay algunas diferencias.  Por ejemplo, la referencia cultural de todos los idiomas especifica el formato de hora de 24 horas en lugar del formato de 12 horas.  
  
 Para convertir una fecha a la cadena de la referencia cultural, pase el objeto <xref:System.Globalization.CultureInfo> al método <xref:System.DateTime.ToString%28System.IFormatProvider%29> del objeto de fecha.  Por ejemplo, el código siguiente muestra "07\/04\/2005 00:00:00", independientemente de la configuración de la referencia cultural de la aplicación.  
  
 [!code-vb[VbVbalrConcepts#1](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/how-culture-affects-strings_1.vb)]  
  
> [!NOTE]
>  Los literales de fecha siempre se interpretan según la referencia cultural inglesa.  
  
## Comparar cadenas  
 Existen dos situaciones importantes donde se necesitan las comparaciones de cadenas:  
  
-   **Ordenar datos para la presentación al usuario.** Utilice operaciones basadas en la referencia cultural actual para que las cadenas se ordenen correctamente.  
  
-   **Determinar si dos cadenas internas de la aplicación coinciden de forma exacta \(normalmente por motivos de seguridad\).** Utilice operaciones que no tengan en cuenta la referencia cultural actual.  
  
 Puede realizar ambos tipos de comparación con la función <xref:Microsoft.VisualBasic.Strings.StrComp%2A> de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  Especifique el argumento opcional `Compare` para controlar el tipo de comparación: `Text` para la mayoría de las entradas y salidas, `Binary` para determinar las coincidencias exactas.  
  
 La función `StrComp` devuelve un entero que indica la relación entre las dos cadenas comparadas basándose en el criterio de ordenación.  Un resultado con un valor positivo indica que la primera cadena es mayor que la segunda.  Un resultado negativo indica que la primera cadena es más pequeña y cero indica igualdad entre las dos cadenas.  
  
 [!code-vb[VbVbalrStrings#22](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_2.vb)]  
  
 También puede usar el equivalente en [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] de la función `StrComp`, es decir, el método <xref:System.String.Compare%2A?displayProperty=fullName>.  Éste es un método estático sobrecargado de la clase de cadena base.  En el siguiente ejemplo se ilustra cómo se utiliza este método:  
  
 [!code-vb[VbVbalrStrings#48](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_3.vb)]  
  
 Para un control más estricto sobre la realización de las comparaciones, puede utilizar sobrecargas adicionales del método <xref:System.String.Compare%2A>.  Con el método <xref:System.String.Compare%2A?displayProperty=fullName>, puede utilizar el argumento `comparisonType` para especificar qué tipo de comparación se debe utilizar.  
  
||||  
|-|-|-|  
|Valor para el argumento `comparisonType`|Tipo de comparación|Cuándo utilizarlo|  
|`Ordinal`|Comparación basada en los bytes del componente de las cadenas.|Utilice este valor al comparar identificadores con distinción entre mayúsculas y minúsculas, configuración relacionada con seguridad u otros identificadores no lingüísticos donde los bytes deben coincidir exactamente.|  
|`OrdinalIgnoreCase`|Comparación basada en los bytes del componente de las cadenas.<br /><br /> `OrdinalIgnoreCase` utiliza la información de la referencia cultural de todos los idiomas para determinar si dos caracteres sólo se diferencian por el uso de mayúsculas.|Utilice este valor al comparar identificadores sin distinción entre mayúsculas y minúsculas, configuración relacionada con seguridad y datos almacenaron en Windows.|  
|`CurrentCulture` o `CurrentCultureIgnoreCase`|Comparación basada en la interpretación de las cadenas en la referencia cultural actual.|Utilice estos valores al comparar datos que se muestran al usuario, la mayor parte de los datos proporcionados por el usuario y otros datos que requieren interpretación lingüística.|  
|`InvariantCulture` o `InvariantCultureIgnoreCase`|Comparación basada en la interpretación de las cadenas en la referencia cultural de todos los idiomas.<br /><br /> Es diferente de `Ordinal` y `OrdinalIgnoreCase`, porque la referencia cultural de todos los idiomas trata los caracteres fuera de su intervalo aceptado como caracteres de todos los idiomas equivalentes.|Utilice estos valores únicamente al comparar datos persistentes o mostrar datos lingüísticamente pertinentes que requieren un criterio de ordenación fijo.|  
  
### Consideraciones de seguridad  
 Si la aplicación toma decisiones sobre la seguridad basándose en el resultado de una comparación o de una operación de cambio de mayúsculas y minúsculas, la operación debe utilizar el método <xref:System.String.Compare%2A?displayProperty=fullName> y pasar `Ordinal` o `OrdinalIgnoreCase` al argumento `comparisonType`.  
  
## Vea también  
 <xref:System.Globalization.CultureInfo>   
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)   
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)