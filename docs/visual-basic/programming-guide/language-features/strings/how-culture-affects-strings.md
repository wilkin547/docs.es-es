---
title: Cómo afecta la referencia cultural a las cadenas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- locale [Visual Basic], effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
ms.openlocfilehash: 41fd612695fbeacbc7b53cb9e5dbf67939e73482
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654744"
---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Cómo afecta la referencia cultural a las cadenas en Visual Basic
Esta página de ayuda describe cómo Visual Basic utiliza la información de referencia cultural para realizar conversiones de cadenas y comparaciones.  
  
## <a name="when-to-use-culture-specific-strings"></a>Cuándo utilizar las cadenas específicas de la referencia cultural  
 Por lo general, debe utilizar cadenas específicas de la referencia cultural para todos los datos que se presentan a y de lectura de los usuarios y utilizar cadenas de referencia cultural de todos los idiomas para los datos de aplicación interna.  
  
 Por ejemplo, si la aplicación pide a los usuarios escriban una fecha como una cadena, deben esperar que los usuarios para dar formato a las cadenas de acuerdo con su referencia cultural y la aplicación debe convertir la cadena correctamente. Si la aplicación, a continuación, presenta esa fecha en su interfaz de usuario, debe presentar en la referencia cultural del usuario.  
  
 Sin embargo, si la aplicación carga la fecha en un servidor central, debe dar formato a la cadena de acuerdo con una referencia cultural concreta, para evitar la confusión entre los formatos de fecha potencialmente diferentes.  
  
## <a name="culture-sensitive-functions"></a>Funciones de la cuenta de la referencia cultural  
 Todas las funciones de conversión de cadenas de Visual Basic (excepto para la `Str` y `Val` funciones) utilizar información de referencia cultural de la aplicación para asegurarse de que las conversiones y comparaciones son adecuadas para la referencia cultural de la aplicación usuario.  
  
 La clave para utilizar correctamente las funciones de conversión de cadenas en aplicaciones que se ejecutan en equipos con la configuración de referencia cultural diferente consiste en comprender qué funciones utilizan una configuración de referencia cultural específica y que usan la configuración de la referencia cultural actual. Tenga en cuenta que la configuración de referencia cultural de la aplicación es, de forma predeterminada, hereda de la configuración de referencia cultural del sistema operativo. Para obtener más información, consulte <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>, y [funciones de conversión de tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 El `Str` (convierte números en cadenas) y `Val` funciones (convierte cadenas a números) no utilizan información de referencia cultural de la aplicación al convertir entre cadenas y números. En su lugar, reconoce el punto (.) como separador decimal válido. La referencia cultural compatible con análogos de estas funciones son:  
  
-   **Conversiones que utilizan la referencia cultural actual.** El `CStr` y `Format` funciones convierten un número en una cadena y el `CDbl` y `CInt` funciones convierten una cadena en un número.  
  
-   **Conversiones que utilizan una referencia cultural concreta.** Cada objeto de número tiene un `ToString(IFormatProvider)` método que convierte un número en una cadena, y un `Parse(String, IFormatProvider)` método que convierte una cadena en un número. Por ejemplo, el `Double` tipo proporciona la <xref:System.Double.ToString%28System.IFormatProvider%29> y <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> métodos.  
  
 Para obtener más información, consulte <xref:Microsoft.VisualBasic.Conversion.Str%2A> y <xref:Microsoft.VisualBasic.Conversion.Val%2A>.  
  
## <a name="using-a-specific-culture"></a>Uso de una referencia cultural específica  
 Imagine que está desarrollando una aplicación que envía una fecha (con formato como una cadena) a un servicio Web. En este caso, la aplicación debe utilizar una referencia cultural concreta para la conversión de cadena. Para ilustrar por este motivo, considere el resultado del uso de la fecha <xref:System.DateTime.ToString> método: si la aplicación utiliza ese método para dar formato a la fecha del 4 de julio de 2005, devuelve "7/4/2005 12:00:00 AM" cuando se ejecuta con la referencia cultural inglés de Estados Unidos (en-US), pero devuelve " 04.07.2005 00:00:00 "cuando se ejecuta con la referencia cultural de alemán (de-DE).  
  
 Cuando necesite realizar una conversión de cadena en un formato de referencia cultural concreta, debe usar el `CultureInfo` clase que está integrado en el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Puede crear un nuevo `CultureInfo` objeto para una referencia cultural concreta, pasando el nombre de la referencia cultural para la <xref:System.Globalization.CultureInfo.%23ctor%2A> constructor. Los nombres de referencias culturales admitidos se enumeran en la <xref:System.Globalization.CultureInfo> página de Ayuda de la clase.  
  
 Como alternativa, puede obtener una instancia de la *una referencia cultural invariable* desde el <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> propiedad. La referencia cultural de todos los idiomas se basa en la configuración regional inglesa, pero hay algunas diferencias. Por ejemplo, la referencia cultural invariable especifica un reloj de 24 horas en lugar de un reloj de 12 horas.  
  
 Para convertir una fecha en la cadena de la referencia cultural, pase el <xref:System.Globalization.CultureInfo> objeto con el objeto de fecha <xref:System.DateTime.ToString%28System.IFormatProvider%29> método. Por ejemplo, el código siguiente muestra "07/04/2005 00:00:00", independientemente de la configuración de referencia cultural de la aplicación.  
  
 [!code-vb[VbVbalrConcepts#1](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/how-culture-affects-strings_1.vb)]  
  
> [!NOTE]
>  Literales de fecha siempre se interpretan según la configuración regional inglesa.  
  
## <a name="comparing-strings"></a>Comparar cadenas  
 Existen dos situaciones importantes donde se necesitan las comparaciones de cadenas:  
  
-   **Ordenar datos para mostrar al usuario.** Use operaciones basadas en la referencia cultural actual, por lo que las cadenas se ordenen correctamente.  
  
-   **Determinar si dos cadenas internas de la aplicación coincidir exactamente con (normalmente por motivos de seguridad).** Utilice las operaciones que pasar por alto la referencia cultural actual.  
  
 Puede realizar dos tipos de comparaciones con Visual Basic <xref:Microsoft.VisualBasic.Strings.StrComp%2A> función. Especifique el valor opcional `Compare` argumento para controlar el tipo de comparación: `Text` para la mayoría de entrada y salida `Binary` para determinar las coincidencias exactas.  
  
 El `StrComp` función devuelve un entero que indica la relación entre las dos cadenas comparadas basándose en el criterio de ordenación. Un valor positivo para el resultado indica que la primera cadena es mayor que la segunda cadena. Un resultado negativo indica que la primera cadena es menor y cero indica que las cadenas son iguales.  
  
 [!code-vb[VbVbalrStrings#22](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_2.vb)]  
  
 También puede usar el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] asociado de la `StrComp` función, el <xref:System.String.Compare%2A?displayProperty=nameWithType> método. Se trata de un método estático, sobrecargado de la clase base string. En el ejemplo siguiente se muestra cómo se utiliza este método:  
  
 [!code-vb[VbVbalrStrings#48](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_3.vb)]  
  
 Para un mayor control sobre cómo se realizan las comparaciones, puede utilizar las sobrecargas adicionales de la <xref:System.String.Compare%2A> método. Con el <xref:System.String.Compare%2A?displayProperty=nameWithType> método, puede usar el `comparisonType` argumento para especificar qué tipo de comparación que se va a usar.  
  
|Valor `comparisonType` argumento|Tipo de comparación|Cuándo utilizarlo|  
|---|---|---|  
|`Ordinal`|Comparación basada en bytes del componente de las cadenas.|Use este valor al comparar: identificadores entre mayúsculas y minúsculas, las configuraciones relacionadas con la seguridad u otros identificadores no lingüísticos donde los bytes deben coincidir exactamente.|  
|`OrdinalIgnoreCase`|Comparación basada en bytes del componente de las cadenas.<br /><br /> `OrdinalIgnoreCase` usa la información de referencia cultural invariable para determinar si dos caracteres solo difieren en mayúsculas y minúsculas.|Use este valor al comparar: identificadores entre mayúsculas y minúsculas, configuración relacionada con la seguridad y los datos almacenados en Windows.|  
|`CurrentCulture` o `CurrentCultureIgnoreCase`|Comparación basada en la interpretación de las cadenas en la referencia cultural actual.|Utilice estos valores al comparar: datos que se muestran al usuario, la mayoría proporcionados por el usuario y otros datos que requieran interpretación lingüística.|  
|`InvariantCulture` o `InvariantCultureIgnoreCase`|Comparación basada en la interpretación de las cadenas en la referencia cultural invariable.<br /><br /> Esto es diferente de la `Ordinal` y `OrdinalIgnoreCase`, porque la referencia cultural de todos los idiomas trata los caracteres fuera de su intervalo aceptado como caracteres invariables equivalentes.|Utilice estos valores únicamente al comparar datos persistentes o mostrar datos lingüísticamente pertinentes requiere un criterio de ordenación fijo.|  
  
### <a name="security-considerations"></a>Consideraciones de seguridad  
 Si la aplicación toma decisiones de seguridad en función del resultado de una comparación o la operación de cambio de mayúsculas y, a continuación, la operación debe utilizar el <xref:System.String.Compare%2A?displayProperty=nameWithType> método y pase `Ordinal` o `OrdinalIgnoreCase` para el `comparisonType` argumento.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Globalization.CultureInfo>  
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
