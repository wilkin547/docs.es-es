---
title: La referencia cultural afecta a cadenas en Visual Basic | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- locale, effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 63228a40897b29d0324be73ca1a17bcb19af2a16
ms.lasthandoff: 03/13/2017

---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Cómo afecta la referencia cultural a las cadenas en Visual Basic
Esta página de ayuda explica cómo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] utiliza la información para realizar las conversiones de cadenas y comparaciones de referencia cultural.  
  
## <a name="when-to-use-culture-specific-strings"></a>Cuándo utilizar las cadenas específicas de la referencia cultural  
 Normalmente, utilizar cadenas específicas de la referencia cultural de todos los datos que se presentan a y de lectura de los usuarios y utilizar cadenas de referencia cultural para los datos de aplicación interno.  
  
 Por ejemplo, si la aplicación pide a los usuarios escribir una fecha como una cadena, debe esperar que los usuarios para dar formato a las cadenas según su referencia cultural y la aplicación debe convertir la cadena correctamente. Si, a continuación, la aplicación presenta esta fecha en su interfaz de usuario, debe presentarla en la referencia cultural del usuario.  
  
 Sin embargo, si la aplicación carga la fecha en un servidor central, debe dar formato a la cadena de acuerdo con una referencia cultural específica, para evitar la confusión entre los formatos de fecha potencialmente diferentes.  
  
## <a name="culture-sensitive-functions"></a>Funciones de la referencia cultural  
 Todos los [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] funciones de conversión de cadenas (excepto para la `Str` y `Val` funciones) Utilice la información de referencia cultural de la aplicación para asegurarse de que las conversiones y comparaciones son adecuadas para la referencia cultural del usuario de la aplicación.  
  
 La clave para utilizar correctamente las funciones de conversión de cadenas en aplicaciones que se ejecutan en equipos con la configuración de referencia cultural diferente es comprender qué funciones utilizan una configuración de referencia cultural específica y que usan la configuración de la referencia cultural actual. Observe que configuración de referencia cultural de la aplicación es, de forma predeterminada, heredada de la configuración de la referencia cultural del sistema operativo. Para obtener más información, vea <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>, y [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</xref:Microsoft.VisualBasic.Conversion.Oct%2A> </xref:Microsoft.VisualBasic.Conversion.Hex%2A> </xref:Microsoft.VisualBasic.Strings.Format%2A> </xref:Microsoft.VisualBasic.Strings.ChrW%2A> </xref:Microsoft.VisualBasic.Strings.Chr%2A> </xref:Microsoft.VisualBasic.Strings.AscW%2A> </xref:Microsoft.VisualBasic.Strings.Asc%2A>  
  
 El `Str` (convierte números en cadenas) y `Val` funciones (convierte cadenas a números) no utilizan la información de referencia cultural de la aplicación al convertir entre cadenas y números. En su lugar, que reconocen el punto (.) como separador decimal válido. La referencia cultural compatible con análogos de estas funciones son:  
  
-   **Conversiones que utilizan la referencia cultural actual.** El `CStr` y `Format` funciones convierten un número en una cadena y el `CDbl` y `CInt` funciones convierten una cadena en un número.  
  
-   **Conversiones que utilizan una referencia cultural concreta.** Cada objeto number tiene un `ToString(IFormatProvider)` método que convierte un número en una cadena y un `Parse(String, IFormatProvider)` método que convierte una cadena en un número. Por ejemplo, el `Double` tipo proporciona el <xref:System.Double.ToString%28System.IFormatProvider%29>y <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29>métodos.</xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> </xref:System.Double.ToString%28System.IFormatProvider%29>  
  
 Para obtener más información, consulte <xref:Microsoft.VisualBasic.Conversion.Str%2A>y <xref:Microsoft.VisualBasic.Conversion.Val%2A>.</xref:Microsoft.VisualBasic.Conversion.Val%2A> </xref:Microsoft.VisualBasic.Conversion.Str%2A>  
  
## <a name="using-a-specific-culture"></a>Uso de una referencia cultural específica  
 Imagine que está desarrollando una aplicación que envía una fecha (con formato como una cadena) a un servicio Web. En este caso, la aplicación debe utilizar una referencia cultural concreta para la conversión de cadena. Para ilustrar por qué, considere el resultado de utilizar la fecha <xref:System.DateTime.ToString>método: si la aplicación utiliza ese método para dar formato a la fecha 4 de julio de 2005, devuelve "7/4/2005 12:00:00 AM" cuando se ejecuta con la referencia cultural inglés de Estados Unidos (en-US), pero devuelve "04.07.2005 00:00:00" cuando se ejecuta con la referencia cultural de alemán (de-DE).</xref:System.DateTime.ToString>  
  
 Cuando necesite realizar una conversión de cadena en un formato de referencia cultural concreta, debe usar el `CultureInfo` (clase) que está integrado en el [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Puede crear un nuevo `CultureInfo` objeto para una referencia cultural concreta pasando el nombre de la referencia cultural a la <xref:System.Globalization.CultureInfo.%23ctor%2A>constructor.</xref:System.Globalization.CultureInfo.%23ctor%2A> Se muestran los nombres de referencia cultural admitida en la <xref:System.Globalization.CultureInfo>página de Ayuda de la clase.</xref:System.Globalization.CultureInfo>  
  
 Como alternativa, puede obtener una instancia de la *referencia cultural invariable* desde el <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>propiedad.</xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> La referencia cultural se basa en la referencia cultural inglesa, pero hay algunas diferencias. Por ejemplo, la referencia cultural invariable especifica un reloj de 24 horas en lugar de un reloj de 12 horas.  
  
 Para convertir una fecha a la cadena de la referencia cultural, pase el <xref:System.Globalization.CultureInfo>con el objeto de fecha <xref:System.DateTime.ToString%28System.IFormatProvider%29>método.</xref:System.DateTime.ToString%28System.IFormatProvider%29> </xref:System.Globalization.CultureInfo> Por ejemplo, el código siguiente muestra "07/04/2005 00:00:00", independientemente de la configuración de la referencia cultural de la aplicación.  
  
 [!code-vb[1 VbVbalrConcepts](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/how-culture-affects-strings_1.vb)]  
  
> [!NOTE]
>  Literales de fecha siempre se interpretan según la referencia cultural inglesa.  
  
## <a name="comparing-strings"></a>Comparar cadenas  
 Hay dos situaciones importantes donde se necesitan las comparaciones de cadenas:  
  
-   **Ordenar datos para mostrar al usuario.** Use operaciones basadas en la referencia cultural actual, por lo que las cadenas se ordenen correctamente.  
  
-   **Determinar si dos cadenas internas de la aplicación coinciden exactamente con (normalmente por motivos de seguridad).** Utilice las operaciones que pase por alto la referencia cultural actual.  
  
 Puede realizar ambos tipos de comparaciones con la [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Strings.StrComp%2A>función.</xref:Microsoft.VisualBasic.Strings.StrComp%2A> Especifique el valor opcional `Compare` argumento para controlar el tipo de comparación: `Text` para la mayoría de entrada y salida `Binary` para determinar las coincidencias exactas.  
  
 El `StrComp` función devuelve un entero que indica la relación entre las dos cadenas comparadas basándose en el criterio de ordenación. Un valor positivo para el resultado indica que la primera cadena es mayor que la segunda cadena. Un resultado negativo indica que la primera cadena es más pequeña y cero indica que las cadenas son iguales.  
  
 [!code-vb[VbVbalrStrings&#22;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_2.vb)]  
  
 También puede utilizar el [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] asociado de la `StrComp` (función), el <xref:System.String.Compare%2A?displayProperty=fullName>método.</xref:System.String.Compare%2A?displayProperty=fullName> Se trata de un método estático sobrecargado de la clase de cadena base. En el ejemplo siguiente se muestra cómo se utiliza este método:  
  
 [!code-vb[VbVbalrStrings Nº&48;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_3.vb)]  
  
 Para un mayor control sobre cómo se realizan las comparaciones, puede utilizar sobrecargas adicionales de la <xref:System.String.Compare%2A>método.</xref:System.String.Compare%2A> Con el <xref:System.String.Compare%2A?displayProperty=fullName>método, puede usar el `comparisonType` argumento para especificar qué tipo de comparación que se va a usar.</xref:System.String.Compare%2A?displayProperty=fullName>  
  
|Valor `comparisonType` argumento|Tipo de comparación|Cuándo utilizarlo|  
|---|---|---|  
|`Ordinal`|Comparación basada en bytes del componente de las cadenas.|Utilice este valor al comparar: identificadores entre mayúsculas y minúsculas, configuración de seguridad u otros identificadores no lingüísticos donde los bytes deben coincidir exactamente.|  
|`OrdinalIgnoreCase`|Comparación basada en bytes del componente de las cadenas.<br /><br /> `OrdinalIgnoreCase`utiliza la información de referencia cultural invariable para determinar si dos caracteres sólo difieren en mayúsculas y minúsculas.|Utilice este valor al comparar: identificadores entre mayúsculas y minúsculas, configuración de seguridad y los datos almacenados en Windows.|  
|`CurrentCulture` o `CurrentCultureIgnoreCase`|Comparación basada en la interpretación de las cadenas en la referencia cultural actual.|Utilice estos valores al comparar: datos que se muestran al usuario, la mayoría proporcionados por el usuario y otros datos que requieren interpretación lingüística.|  
|`InvariantCulture` o `InvariantCultureIgnoreCase`|Comparación basada en la interpretación de las cadenas en la referencia cultural invariable.<br /><br /> Esto es diferente de la `Ordinal` y `OrdinalIgnoreCase`, porque la referencia cultural de todos los idiomas trata los caracteres fuera de su intervalo aceptado como caracteres invariables equivalentes.|Utilice estos valores únicamente al comparar datos persistentes o mostrar datos lingüísticamente pertinentes que requiere un criterio de ordenación fijo.|  
  
### <a name="security-considerations"></a>Consideraciones de seguridad  
 Si la aplicación toma decisiones de seguridad basándose en el resultado de una comparación o la operación de cambio de mayúsculas y, a continuación, la operación debe utilizar el <xref:System.String.Compare%2A?displayProperty=fullName>método y pasar `Ordinal` o `OrdinalIgnoreCase` para el `comparisonType` argumento.</xref:System.String.Compare%2A?displayProperty=fullName>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Globalization.CultureInfo></xref:System.Globalization.CultureInfo>   
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)   
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
