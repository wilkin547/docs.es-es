---
title: Constantes y enumeraciones (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- enumerations [Visual Basic]
- constants
- constants, list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
caps.latest.revision: 18
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
ms.openlocfilehash: e37ef2e3c51e96e85cb214054195016e69d52382
ms.lasthandoff: 03/13/2017

---
# <a name="constants-and-enumerations-visual-basic"></a>Constantes y enumeraciones (Visual Basic)
[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Proporciona un número de constantes y enumeraciones para desarrolladores predefinidas. Las constantes almacenan valores que permanecen constantes durante la ejecución de una aplicación. Las enumeraciones proporcionan una forma cómoda para trabajar con conjuntos de constantes relacionadas y asociar valores constantes con nombres.  
  
## <a name="constants"></a>Constantes  
  
### <a name="conditional-compilation-constants"></a>Constantes de compilación condicional  
 La tabla siguiente enumeran las constantes predefinidas disponibles para la compilación condicional.  
  
|**Constante**|**Descripción**|  
|---|---|  
|`CONFIG`|Una cadena que corresponde a la configuración actual de la **configuración de soluciones activas** cuadro el **Configuration Manager**.|  
|`DEBUG`|Un `Boolean` valor que se puede establecer en el **propiedades del proyecto** cuadro de diálogo. De forma predeterminada, se define la configuración de depuración de un proyecto `DEBUG`. Cuando `DEBUG` definido, <xref:System.Diagnostics.Debug>clase métodos generan resultados en la **salida** ventana.</xref:System.Diagnostics.Debug> Si no está definido, <xref:System.Diagnostics.Debug>métodos de clase no se compilan y no se generan resultados.</xref:System.Diagnostics.Debug>|  
|`TARGET`|Una cadena que representa el tipo de salida para el proyecto o la configuración de la línea de comandos **/target** opción. Los valores posibles de `TARGET` son:<br /><br /> -"winexe" para una aplicación de Windows.<br />-"exe" para una aplicación de consola.<br />-"library" para una biblioteca de clases.<br />-"module" para un módulo.<br />-El **/target** opción se puede establecer el [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)] entorno de desarrollo integrado. Para obtener más información, consulte [/target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Un `Boolean` valor que se puede establecer en el **propiedades del proyecto** cuadro de diálogo. De forma predeterminada, se definen todas las configuraciones para un proyecto `TRACE`. Cuando `TRACE` definido, <xref:System.Diagnostics.Trace>clase métodos generan resultados en la **salida** ventana.</xref:System.Diagnostics.Trace> Si no está definido, <xref:System.Diagnostics.Trace>clase métodos no se compilan y no `Trace` se generan resultados.</xref:System.Diagnostics.Trace>|  
|`VBC_VER`|Un número que representa la [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] versión, en *principal*.* menores* formato. El número de versión para [!INCLUDE[vbprvblong](../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] es 8.0.|  
  
### <a name="print-and-display-constants"></a>Constantes de impresión y visualización  
 Cuando llame a imprimir y mostrar las funciones, puede utilizar las siguientes constantes en el código en lugar de los valores reales.  
  
|**Constante**|**Descripción**|  
|---|---|  
|`vbCrLf`|Combinación de caracteres de retorno y avance de carro.|  
|`vbCr`|Carácter de retorno de carro.|  
|`vbLf`|Carácter de avance de línea.|  
|`vbNewLine`|Carácter de nueva línea.|  
|`vbNullChar`|Carácter nulo.|  
|`vbNullString`|No es igual que una cadena de longitud cero (""); se utiliza para llamar a procedimientos externos.|  
|`vbObjectError`|Número de error. Números de error definidos por el usuario deben ser mayores que este valor. Por ejemplo:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Carácter de tabulación.|  
|`vbBack`|Carácter de retroceso.|  
|`vbFormFeed`|No se utiliza en Microsoft Windows.|  
|`vbVerticalTab`|No resulta útil en Microsoft Windows.|  
  
## <a name="enumerations"></a>Enumeraciones  
 La tabla siguiente se enumeran y describen las enumeraciones proporcionadas por [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
|Enumeración|Descripción|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle></xref:Microsoft.VisualBasic.AppWinStyle>|Indica el estilo de ventana que se utilizará para el programa invocado cuando se llama a la <xref:Microsoft.VisualBasic.Interaction.Shell%2A>función.</xref:Microsoft.VisualBasic.Interaction.Shell%2A>|  
|<xref:Microsoft.VisualBasic.AudioPlayMode></xref:Microsoft.VisualBasic.AudioPlayMode>|Indica cómo reproducir sonidos al llamar a métodos de audio.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole></xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Indica el tipo de rol que se comprueba al llamar a la <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>método.</xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
|<xref:Microsoft.VisualBasic.CallType></xref:Microsoft.VisualBasic.CallType>|Indica el tipo de procedimiento que se invoca cuando se llama a la <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>función.</xref:Microsoft.VisualBasic.Interaction.CallByName%2A>|  
|<xref:Microsoft.VisualBasic.CompareMethod></xref:Microsoft.VisualBasic.CompareMethod>|Indica cómo comparar cadenas al llamar a funciones de comparación.|  
|<xref:Microsoft.VisualBasic.DateFormat></xref:Microsoft.VisualBasic.DateFormat>|Indica cómo se muestran las fechas cuando se llama a la <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>función.</xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|  
|<xref:Microsoft.VisualBasic.DateInterval></xref:Microsoft.VisualBasic.DateInterval>|Indica cómo determinar y dar formato a los intervalos de fecha al llamar a funciones relacionadas con fechas.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption></xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Especifica qué se debe hacer cuando un directorio que se va a eliminar contiene archivos o directorios.|  
|<xref:Microsoft.VisualBasic.DueDate></xref:Microsoft.VisualBasic.DueDate>|Indica cuándo vencen los pagos al llamar a métodos financieros.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType></xref:Microsoft.VisualBasic.FileIO.FieldType>|Indica si los campos de texto están delimitados o ancho fijo.|  
|<xref:Microsoft.VisualBasic.FileAttribute></xref:Microsoft.VisualBasic.FileAttribute>|Indica los atributos de archivo que se utilizará al llamar a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek></xref:Microsoft.VisualBasic.FirstDayOfWeek>|Indica el primer día de la semana que se utilizará al llamar a funciones relacionadas con fechas.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear></xref:Microsoft.VisualBasic.FirstWeekOfYear>|Indica la primera semana del año que se va a usar al llamar a funciones relacionadas con fechas.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult></xref:Microsoft.VisualBasic.MsgBoxResult>|Indica qué botón se ha presionado en un cuadro de mensaje, devuelto por la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>función.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle></xref:Microsoft.VisualBasic.MsgBoxStyle>|Indica qué botones se mostrarán cuando se llama a la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>función.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>|  
|<xref:Microsoft.VisualBasic.OpenAccess></xref:Microsoft.VisualBasic.OpenAccess>|Indica cómo abrir un archivo al llamar a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.OpenMode></xref:Microsoft.VisualBasic.OpenMode>|Indica cómo abrir un archivo al llamar a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.OpenShare></xref:Microsoft.VisualBasic.OpenShare>|Indica cómo abrir un archivo al llamar a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption></xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Especifica si un archivo se debería eliminar permanentemente o colocar en la Papelera de reciclaje.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption></xref:Microsoft.VisualBasic.FileIO.SearchOption>|Especifica si se debe buscar todos o sólo los directorios de nivel superior.|  
|<xref:Microsoft.VisualBasic.TriState></xref:Microsoft.VisualBasic.TriState>|Indica un `Boolean` valor o si se debe utilizar el valor predeterminado al llamar a funciones de formato numérico.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption></xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Especifica qué debe hacer si el usuario hace clic **cancelar** durante una operación.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption></xref:Microsoft.VisualBasic.FileIO.UIOption>|Especifica si se debe o no mostrar un cuadro de diálogo de progreso al copiar, eliminar o mover archivos o directorios.|  
|<xref:Microsoft.VisualBasic.VariantType></xref:Microsoft.VisualBasic.VariantType>|Indica el tipo de un objeto variant, devuelto por la <xref:Microsoft.VisualBasic.Information.VarType%2A>función.</xref:Microsoft.VisualBasic.Information.VarType%2A>|  
|<xref:Microsoft.VisualBasic.VbStrConv></xref:Microsoft.VisualBasic.VbStrConv>|Indica qué tipo de conversión se realiza cuando se llama a la <xref:Microsoft.VisualBasic.Strings.StrConv%2A>función.</xref:Microsoft.VisualBasic.Strings.StrConv%2A>|  
  
## <a name="see-also"></a>Vea también  
 [Referencia del lenguaje Visual Basic](../../visual-basic/language-reference/index.md)   
 [Visual Basic](../../visual-basic/index.md)   
 [Información general de constantes](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Información general sobre las enumeraciones](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
