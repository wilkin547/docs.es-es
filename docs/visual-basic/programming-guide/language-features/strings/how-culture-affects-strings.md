---
title: Cómo afecta la referencia cultural a las cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- locale [Visual Basic], effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
ms.openlocfilehash: 2520a7684b8710abd949543e3f17f77d3c631d22
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352478"
---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Cómo afecta la referencia cultural a las cadenas en Visual Basic
En esta página de ayuda se describe cómo Visual Basic usa la información de referencia cultural para realizar conversiones de cadenas y comparaciones.  
  
## <a name="when-to-use-culture-specific-strings"></a>Cuándo usar cadenas específicas de la referencia cultural  
 Normalmente, debe usar cadenas específicas de la referencia cultural para todos los datos presentados y leídos de los usuarios, y usar cadenas de referencia cultural invariable para los datos internos de la aplicación.  
  
 Por ejemplo, si la aplicación pide a los usuarios que escriban una fecha como una cadena, debería esperar que los usuarios apliquen formato a las cadenas según su referencia cultural y la aplicación debe convertir la cadena de forma adecuada. Si la aplicación presenta esa fecha en su interfaz de usuario, debe presentarla en la referencia cultural del usuario.  
  
 Sin embargo, si la aplicación carga la fecha en un servidor central, debe dar formato a la cadena según una referencia cultural concreta, para evitar confusiones entre formatos de fecha potencialmente diferentes.  
  
## <a name="culture-sensitive-functions"></a>Funciones que tienen en cuenta la referencia cultural  
 Todas las funciones de conversión de cadenas de Visual Basic (excepto las funciones `Str` y `Val`) utilizan la información de la referencia cultural de la aplicación para asegurarse de que las conversiones y comparaciones son adecuadas para la referencia cultural del usuario de la aplicación.  
  
 La clave para usar correctamente las funciones de conversión de cadenas en aplicaciones que se ejecutan en equipos con una configuración de referencia cultural diferente es entender qué funciones usan una configuración de referencia cultural específica y cuáles utilizan la configuración de referencia cultural actual. Tenga en cuenta que la configuración de la referencia cultural de la aplicación se hereda de forma predeterminada de la configuración de referencia cultural del sistema operativo. Para obtener más información, vea <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>y [funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 El `Str` (convierte números en cadenas) y `Val` (convierte cadenas en números) las funciones no usan la información de referencia cultural de la aplicación al realizar la conversión entre cadenas y números. En su lugar, reconocen solo el punto (.) como separador decimal válido. Los análogos que tienen en cuenta la referencia cultural de estas funciones son:  
  
- **Conversiones que usan la referencia cultural actual.** Las funciones `CStr` y `Format` convierten un número en una cadena y las funciones `CDbl` y `CInt` convierten una cadena en un número.  
  
- **Conversiones que usan una referencia cultural concreta.** Cada objeto Number tiene un método `ToString(IFormatProvider)` que convierte un número en una cadena y un método `Parse(String, IFormatProvider)` que convierte una cadena en un número. Por ejemplo, el tipo de `Double` proporciona los métodos <xref:System.Double.ToString%28System.IFormatProvider%29> y <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29>.  
  
 Para obtener más información, vea <xref:Microsoft.VisualBasic.Conversion.Str%2A> y <xref:Microsoft.VisualBasic.Conversion.Val%2A>.  
  
## <a name="using-a-specific-culture"></a>Usar una referencia cultural específica  
 Imagine que está desarrollando una aplicación que envía una fecha (con formato de cadena) a un servicio Web. En este caso, la aplicación debe usar una referencia cultural específica para la conversión de cadenas. Para ilustrar por qué, tenga en cuenta el resultado de utilizar el método de <xref:System.DateTime.ToString> de la fecha: Si la aplicación usa ese método para dar formato a la fecha del 4 de julio de 2005, devuelve "7/4/2005 12:00:00 AM" cuando se ejecuta con la referencia cultural de Estados Unidos inglés (en-US), pero devuelve "04.07.2005 00:00:00" cuando se ejecuta con la referencia cultural de alemán  
  
 Cuando necesite realizar una conversión de cadena en un formato de referencia cultural concreto, debe utilizar la clase `CultureInfo` que está integrada en el .NET Framework. Puede crear un nuevo objeto `CultureInfo` para una referencia cultural concreta pasando el nombre de la referencia cultural al constructor <xref:System.Globalization.CultureInfo.%23ctor%2A>. Los nombres de referencia cultural admitidos se enumeran en la página de ayuda de la clase <xref:System.Globalization.CultureInfo>.  
  
 Como alternativa, puede obtener una instancia de la *referencia cultural de todos los idiomas* de la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. La referencia cultural de todos los idiomas se basa en la referencia cultural en inglés, pero hay algunas diferencias. Por ejemplo, la referencia cultural de todos los idiomas especifica un reloj de 24 horas en lugar de un reloj de 12 horas.  
  
 Para convertir una fecha en la cadena de la referencia cultural, pase el objeto <xref:System.Globalization.CultureInfo> al método <xref:System.DateTime.ToString%28System.IFormatProvider%29> del objeto Date. Por ejemplo, el código siguiente muestra "07/04/2005 00:00:00", independientemente de la configuración de la referencia cultural de la aplicación.  
  
 [!code-vb[VbVbalrConcepts#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#1)]  
  
> [!NOTE]
> Los literales de fecha siempre se interpretan según la referencia cultural en inglés.  
  
## <a name="comparing-strings"></a>Comparar cadenas  
 Hay dos situaciones importantes en las que se necesitan comparaciones de cadenas:  
  
- **Ordenación de los datos que se van a mostrar al usuario.** Utilice operaciones basadas en la referencia cultural actual para que las cadenas se ordenen correctamente.  
  
- **Determinar si dos cadenas internas de aplicación coinciden exactamente (normalmente por motivos de seguridad).** Usar operaciones que omitan la referencia cultural actual.  
  
 Puede realizar ambos tipos de comparaciones con la Visual Basic <xref:Microsoft.VisualBasic.Strings.StrComp%2A> función. Especifique el argumento opcional `Compare` para controlar el tipo de comparación: `Text` para la mayoría de los `Binary` de entrada y salida para determinar las coincidencias exactas.  
  
 La función `StrComp` devuelve un entero que indica la relación entre las dos cadenas comparadas en función del criterio de ordenación. Un valor positivo para el resultado indica que la primera cadena es mayor que la segunda cadena. Un resultado negativo indica que la primera cadena es más pequeña y cero indica la igualdad entre las cadenas.  
  
 [!code-vb[VbVbalrStrings#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#22)]  
  
 También puede usar el .NET Framework asociado de la función `StrComp`, el método <xref:System.String.Compare%2A?displayProperty=nameWithType>. Este es un método estático y sobrecargado de la clase de cadena base. En el ejemplo siguiente se muestra cómo se utiliza este método:  
  
 [!code-vb[VbVbalrStrings#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#48)]  
  
 Para tener un mayor control sobre cómo se realizan las comparaciones, puede usar sobrecargas adicionales del método <xref:System.String.Compare%2A>. Con el método <xref:System.String.Compare%2A?displayProperty=nameWithType>, puede usar el argumento `comparisonType` para especificar el tipo de comparación que se va a utilizar.  
  
|Valor para `comparisonType` argumento|Tipo de comparación|Cuándo utilizarlo|  
|---|---|---|  
|`Ordinal`|Comparación basada en bytes de componentes de cadenas.|Use este valor al comparar: identificadores que distinguen mayúsculas de minúsculas, configuraciones relacionadas con la seguridad u otros identificadores no lingüísticos donde los bytes deben coincidir exactamente.|  
|`OrdinalIgnoreCase`|Comparación basada en bytes de componentes de cadenas.<br /><br /> `OrdinalIgnoreCase` usa la información de la referencia cultural de todos los idiomas para determinar si dos caracteres solo se diferencian en el uso de mayúsculas.|Use este valor al comparar: identificadores que no distinguen mayúsculas de minúsculas, configuraciones relacionadas con la seguridad y datos almacenados en Windows.|  
|`CurrentCulture` o `CurrentCultureIgnoreCase`|Comparación basada en la interpretación de las cadenas en la referencia cultural actual.|Use estos valores al comparar: datos que se muestran al usuario, la mayoría de los datos proporcionados por el usuario y otros datos que requieren interpretación lingüística.|  
|`InvariantCulture` o `InvariantCultureIgnoreCase`|Comparación basada en la interpretación de las cadenas en la referencia cultural de todos los idiomas.<br /><br /> Esto es diferente del `Ordinal` y `OrdinalIgnoreCase`, porque la referencia cultural de todos los idiomas trata los caracteres que están fuera del intervalo aceptado como caracteres invariables equivalentes.|Utilice estos valores solo al comparar datos persistentes o Mostrar datos pertinentes lingüísticamente que requieran un criterio de ordenación fijo.|  
  
### <a name="security-considerations"></a>Consideraciones de seguridad  
 Si la aplicación toma decisiones de seguridad basadas en el resultado de una comparación o de una operación de cambio de mayúsculas y minúsculas, la operación debe utilizar el método <xref:System.String.Compare%2A?displayProperty=nameWithType> y pasar `Ordinal` o `OrdinalIgnoreCase` para el argumento `comparisonType`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Globalization.CultureInfo>
- [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
