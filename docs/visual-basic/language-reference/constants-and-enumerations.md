---
title: Constantes y enumeraciones (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
ms.openlocfilehash: 0a9c01269e12c2d84be4f30c236c439012a88153
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839597"
---
# <a name="constants-and-enumerations-visual-basic"></a>Constantes y enumeraciones (Visual Basic)
Visual Basic proporciona una serie de constantes y enumeraciones para desarrolladores predefinidas. Las constantes almacenan valores que permanecen constantes durante la ejecución de una aplicación. Las enumeraciones proporcionan una forma cómoda de trabajar con conjuntos de constantes relacionadas y asociar valores constantes con nombres.  
  
## <a name="constants"></a>Constantes  
  
### <a name="conditional-compilation-constants"></a>Constantes de compilación condicional  
 En la tabla siguiente se enumera las constantes predefinidas disponibles para la compilación condicional.  
  
|**Constante**|**Descripción**|  
|---|---|  
|`CONFIG`|Una cadena que corresponde a la configuración actual de la **configuración de soluciones activas** cuadro el **Configuration Manager**.|  
|`DEBUG`|Un `Boolean` valor que se puede establecer en el **las propiedades del proyecto** cuadro de diálogo. De forma predeterminada, se define la configuración de depuración para un proyecto `DEBUG`. Cuando `DEBUG` está definido, <xref:System.Diagnostics.Debug> métodos de clase generan resultados en la **salida** ventana. Si no está definido, <xref:System.Diagnostics.Debug> métodos de clase no se compilan y se genera ningún resultado de depuración.|  
|`TARGET`|Una cadena que representa el tipo de salida para el proyecto o la configuración de la línea de comandos **/target** opción. Los valores posibles de `TARGET` son:<br /><br /> -"winexe" para una aplicación de Windows.<br />-"exe" para una aplicación de consola.<br />-"biblioteca" para una biblioteca de clases.<br />-"module" para un módulo.<br />-El **/target** opción se puede establecer en el entorno de desarrollo integrado de Visual Studio. Para obtener más información, consulte [/target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Un `Boolean` valor que se puede establecer en el **las propiedades del proyecto** cuadro de diálogo. De forma predeterminada, todas las configuraciones para un proyecto definen `TRACE`. Cuando `TRACE` está definido, <xref:System.Diagnostics.Trace> métodos de clase generan resultados en la **salida** ventana. Si no está definido, <xref:System.Diagnostics.Trace> no se compilan los métodos de clase y no `Trace` se generan resultados.|  
|`VBC_VER`|Un número que representa la versión de Visual Basic en *principales*. *menores* formato. El número de versión para [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)] es 8.0.|  
  
### <a name="print-and-display-constants"></a>Constantes de impresión y visualización  
 Al llamar a imprimir y mostrar las funciones, puede usar las siguientes constantes en el código en lugar de los valores reales.  
  
|**Constante**|**Descripción**|  
|---|---|  
|`vbCrLf`|Combinación de caracteres / avance de línea de retorno de carro.|  
|`vbCr`|Carácter de retorno de carro.|  
|`vbLf`|Carácter de avance de línea.|  
|`vbNewLine`|Carácter de nueva línea.|  
|`vbNullChar`|Carácter nulo.|  
|`vbNullString`|No es el mismo como una cadena de longitud cero (""); se utiliza para llamar a procedimientos externos.|  
|`vbObjectError`|Número de error. Números de error definido por el usuario deben ser mayores que este valor. Por ejemplo:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Carácter de tabulación.|  
|`vbBack`|Carácter de retroceso.|  
|`vbFormFeed`|No se utiliza en Microsoft Windows.|  
|`vbVerticalTab`|No resulta útil en Microsoft Windows.|  
  
## <a name="enumerations"></a>Enumeraciones  
 En la tabla siguiente se enumera y describe las enumeraciones proporcionadas por Visual Basic.  
  
|Enumeración|Descripción|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Indica el estilo de ventana que se usará para el programa invocado cuando se llama a la <xref:Microsoft.VisualBasic.Interaction.Shell%2A> función.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Indica cómo reproducir sonidos al llamar a métodos de audio.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Indica el tipo de rol que se comprueba cuando se llama a la <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A> método.|  
|<xref:Microsoft.VisualBasic.CallType>|Indica el tipo de procedimiento que se invoca cuando se llama a la <xref:Microsoft.VisualBasic.Interaction.CallByName%2A> función.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Indica cómo comparar cadenas al llamar a funciones de comparación.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Indica cómo mostrar fechas al llamar a la <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A> función.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Indica cómo determinar y dar formato a los intervalos de fecha al llamar a funciones relacionadas con fechas.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Especifica qué se debe hacer cuando un directorio que se va a eliminar contiene archivos o directorios.|  
|<xref:Microsoft.VisualBasic.DueDate>|Indica cuándo vencen los pagos al llamar a métodos financieros.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Indica si los campos de texto están delimitados o ancho fijo.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Indica los atributos de archivo que se usará al llamar a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Indica el primer día de la semana que se utiliza al llamar a funciones relacionadas con fechas.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Indica la primera semana del año que se utiliza al llamar a funciones relacionadas con fechas.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Indica qué botón se ha presionado en un cuadro de mensaje, devuelto por la función <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Indica qué botones se mostrarán cuando se llama a la función <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Indica cómo abrir un archivo al llamar a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Indica cómo abrir un archivo al llamar a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Indica cómo abrir un archivo al llamar a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Especifica si un archivo debe elimina de forma permanente o se colocan en la Papelera de reciclaje.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Especifica si se buscan todos o sólo los directorios de nivel superior.|  
|<xref:Microsoft.VisualBasic.TriState>|Indica un `Boolean` valor o si se debe usar el valor predeterminado cuando se llama a funciones de formato numérico.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Especifica qué debe hacer si el usuario hace clic **cancelar** durante una operación.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Especifica si se deben mostrar un cuadro de diálogo de progreso al copiar, eliminar o mover archivos o directorios.|  
|<xref:Microsoft.VisualBasic.VariantType>|Indica el tipo de un objeto de variante, devuelto por la <xref:Microsoft.VisualBasic.Information.VarType%2A> función.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Indica qué tipo de conversión se realiza cuando se llama a la función <xref:Microsoft.VisualBasic.Strings.StrConv%2A>.|  
  
## <a name="see-also"></a>Vea también

- [Referencia del lenguaje Visual Basic](../../visual-basic/language-reference/index.md)
- [Visual Basic](../../visual-basic/index.md)
- [Información general sobre las constantes](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Información general sobre las enumeraciones](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
