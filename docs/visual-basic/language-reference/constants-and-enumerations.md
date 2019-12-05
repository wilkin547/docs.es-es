---
title: Constantes y enumeraciones
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
ms.openlocfilehash: e47fd1c606f7d4cd0cf2fa6398beaa183ed95076
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838161"
---
# <a name="constants-and-enumerations-visual-basic"></a>Constantes y enumeraciones (Visual Basic)

Visual Basic proporciona varias constantes y enumeraciones predefinidas para los desarrolladores. Las constantes almacenan valores que permanecen constantes a lo largo de la ejecución de una aplicación. Las enumeraciones proporcionan una forma cómoda de trabajar con conjuntos de constantes relacionadas y asociar valores constantes con nombres.  
  
## <a name="constants"></a>Constantes  
  
### <a name="conditional-compilation-constants"></a>Constantes de compilación condicional  

 En la tabla siguiente se enumeran las constantes predefinidas disponibles para la compilación condicional.  
  
|**Constante**|**Descripción**|  
|---|---|  
|`CONFIG`|Cadena que corresponde a la configuración actual del cuadro de **configuración de soluciones activo** en el **Configuration Manager**.|  
|`DEBUG`|`Boolean` valor que se puede establecer en el cuadro de diálogo **propiedades del proyecto** . De forma predeterminada, la configuración de depuración de un proyecto define `DEBUG`. Cuando se define `DEBUG`, <xref:System.Diagnostics.Debug> métodos de clase generan la salida en la ventana de **salida** . Cuando no se define, <xref:System.Diagnostics.Debug> métodos de clase no se compilan y no se generan resultados de depuración.|  
|`TARGET`|Una cadena que representa el tipo de salida del proyecto o la configuración de la opción **/target** de la línea de comandos. Los valores posibles de `TARGET` son:<br /><br /> -"winexe" para una aplicación Windows.<br />-"exe" para una aplicación de consola.<br />-"Library" para una biblioteca de clases.<br />-"Module" para un módulo.<br />-La opción **/target** se puede establecer en el entorno de desarrollo integrado de Visual Studio. Para obtener más información, vea [-target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|`Boolean` valor que se puede establecer en el cuadro de diálogo **propiedades del proyecto** . De forma predeterminada, todas las configuraciones de un proyecto definen `TRACE`. Cuando se define `TRACE`, <xref:System.Diagnostics.Trace> métodos de clase generan la salida en la ventana de **salida** . Cuando no se define, <xref:System.Diagnostics.Trace> métodos de clase no se compilan y no se genera ninguna salida `Trace`.|  
|`VBC_VER`|Un número que representa la versión de Visual Basic, en *major*. formato *secundario* .|  
  
### <a name="print-and-display-constants"></a>Constantes de impresión y visualización  

 Al llamar a las funciones de impresión y visualización, puede usar las siguientes constantes en el código en lugar de los valores reales.  
  
|**Constante**|**Descripción**|  
|---|---|  
|`vbCrLf`|Combinación de caracteres de retorno de carro/avance de carro.|  
|`vbCr`|Carácter de retorno de carro.|  
|`vbLf`|Carácter de avance de la alimentación.|  
|`vbNewLine`|Carácter de nueva línea.|  
|`vbNullChar`|Carácter nulo.|  
|`vbNullString`|No es lo mismo que una cadena de longitud cero (""); se usa para llamar a procedimientos externos.|  
|`vbObjectError`|Número de error. Los números de error definidos por el usuario deben ser mayores que este valor. Por ejemplo:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Carácter de tabulación.|  
|`vbBack`|Carácter de retroceso.|  
|`vbFormFeed`|No se utiliza en Microsoft Windows.|  
|`vbVerticalTab`|No es útil en Microsoft Windows.|  
  
## <a name="enumerations"></a>Enumeraciones  

 En la tabla siguiente se enumeran y se describen las enumeraciones proporcionadas por Visual Basic.  
  
|Enumeración|Descripción|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Indica el estilo de ventana que se va a usar para el programa invocado cuando se llama a la función <xref:Microsoft.VisualBasic.Interaction.Shell%2A>.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Indica cómo reproducir sonidos al llamar a métodos de audio.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Indica el tipo de rol que se va a comprobar cuando se llama al método <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>.|  
|<xref:Microsoft.VisualBasic.CallType>|Indica el tipo de procedimiento que se invoca cuando se llama a la función <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Indica cómo comparar cadenas al llamar a funciones de comparación.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Indica cómo se muestran las fechas cuando se llama a la función <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Indica cómo determinar y dar formato a los intervalos de fecha al llamar a funciones relacionadas con fechas.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Especifica qué se debe hacer cuando un directorio que se va a eliminar contiene archivos o directorios.|  
|<xref:Microsoft.VisualBasic.DueDate>|Indica cuándo vencen los pagos al llamar a métodos financieros.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Indica si los campos de texto son delimitados o de ancho fijo.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Indica los atributos de archivo que se van a usar al llamar a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Indica el primer día de la semana que se va a usar al llamar a funciones relacionadas con fechas.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Indica la primera semana del año que se va a usar al llamar a funciones relacionadas con fechas.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Indica qué botón se ha presionado en un cuadro de mensaje, devuelto por la función <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Indica qué botones se mostrarán cuando se llama a la función <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Indica cómo abrir un archivo cuando se llama a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Indica cómo abrir un archivo cuando se llama a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Indica cómo abrir un archivo cuando se llama a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Especifica si un archivo debe eliminarse de manera permanente o colocarse en la papelera de reciclaje.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Especifica si se van a buscar todos los directorios de nivel superior o solo.|  
|<xref:Microsoft.VisualBasic.TriState>|Indica un valor `Boolean` o si se debe usar el valor predeterminado al llamar a funciones de formato numérico.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Especifica qué se debe hacer si el usuario hace clic en **Cancelar** durante una operación.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Especifica si se muestra o no un cuadro de diálogo de progreso al copiar, eliminar o mover archivos o directorios.|  
|<xref:Microsoft.VisualBasic.VariantType>|Indica el tipo de un objeto Variant, devuelto por la función <xref:Microsoft.VisualBasic.Information.VarType%2A>.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Indica qué tipo de conversión se realiza cuando se llama a la función <xref:Microsoft.VisualBasic.Strings.StrConv%2A>.|  
  
## <a name="see-also"></a>Vea también

- [Referencia del lenguaje Visual Basic](../../visual-basic/language-reference/index.md)
- [Información general sobre las constantes](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Información general sobre las enumeraciones](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
