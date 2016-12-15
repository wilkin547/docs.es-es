---
title: "Constantes y enumeraciones (Visual Basic) | Microsoft Docs"
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
  - "constantes"
  - "constantes, lista"
  - "enumeraciones [Visual Basic]"
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Constantes y enumeraciones (Visual Basic)
[!INCLUDE[vs2017banner](../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona varias constantes y enumeraciones predefinidas para desarrolladores.  Las constantes almacenan valores que permanecen constantes durante la ejecución de una aplicación.  Las enumeraciones proporcionan una forma cómoda de trabajar con conjuntos de constantes relacionadas y de asociar valores de constantes con nombres.  
  
## Constantes  
  
### Constantes de compilación condicional  
 La tabla siguiente lista las constantes predefinidas disponibles para la compilación condicional.  
  
|||  
|-|-|  
|**Constante**|**Descripción**|  
|`CONFIG`|Una cadena que corresponde a la configuración actual del cuadro **Configuración de soluciones activas** en el **Administrador de configuración**.|  
|`DEBUG`|Un valor `Boolean` que se puede establecer en el cuadro de diálogo **Propiedades del proyecto**.  De manera predeterminada, la configuración de depuración para un proyecto define `DEBUG`.  Si está definido `DEBUG`, los métodos de la clase <xref:System.Diagnostics.Debug> generan resultados en la **Ventana de salida**.  Si no está definido, los métodos de la clase <xref:System.Diagnostics.Debug> no se compilan y no se generan resultados de depuración.|  
|`TARGET`|Una cadena que representa el tipo de resultado para el proyecto o la configuración de la opción **\/target** de la línea de comandos.  Los posibles valores de `TARGET` son:<br /><br /> -   "winexe" para una aplicación para Windows.<br />-   "exe" para una aplicación de la consola.<br />-   "library" para una biblioteca de clases.<br />-   "module" para un módulo.<br />-   La opción **\/target** se puede establecer en el entorno de desarrollo integrado de [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)].  Para obtener más información, vea [\/target](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Un valor `Boolean` que se puede establecer en el cuadro de diálogo **Propiedades del proyecto**.  De manera predeterminada, todas las configuraciones para un proyecto definen `TRACE`.  Si está definido `TRACE`, los métodos de la clase <xref:System.Diagnostics.Trace> generan resultados en la **Ventana de salida**.  Si no está definido, los métodos de la clase <xref:System.Diagnostics.Trace> no se compilan y no se generan resultados `Trace`.|  
|`VBC_VER`|Un número que representa la versión de [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], en formato *major*.*minor*.  El número de versión para [!INCLUDE[vbprvblong](../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] es 8.0.|  
  
### Constantes de impresión y presentación  
 Cuando se llama a funciones de impresión y presentación, se pueden utilizar las siguientes constantes en el código en lugar de los valores reales.  
  
|||  
|-|-|  
|**Constante**|**Descripción**|  
|`vbCrLf`|Combinación de caracteres de retorno de carro\/avance de línea.|  
|`vbCr`|Carácter de retorno de carro.|  
|`vbLf`|Carácter de avance de línea.|  
|`vbNewLine`|Carácter de nueva línea.|  
|`vbNullChar`|Carácter nulo.|  
|`vbNullString`|No es lo mismo que una cadena de longitud cero \(""\). Se utiliza para llamar a procedimientos externos.|  
|`vbObjectError`|Número de error.  Los números de error definidos por el usuario deberían ser mayores que este valor.  Por ejemplo:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Carácter de tabulador.|  
|`vbBack`|Carácter de retroceso.|  
|`vbFormFeed`|No se utiliza en Microsoft Windows.|  
|`vbVerticalTab`|No es útil en Microsoft Windows.|  
  
## Enumeraciones  
 En la tabla siguiente se muestran y describen las enumeraciones proporcionadas por [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
|||  
|-|-|  
|Enumeración|Descripción|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Indica el estilo de ventana que se va a utilizar para el programa invocado al llamar a la función <xref:Microsoft.VisualBasic.Interaction.Shell%2A>.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Indica cómo reproducir sonidos al llamar a los métodos de audio.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Indica el tipo de rol que se comprueba cuando se llama al método <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>.|  
|<xref:Microsoft.VisualBasic.CallType>|Indica el tipo de procedimiento que se debe invocar al llamar a la función <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Indica cómo comparar las cadenas cuando se llama a las funciones de comparación.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Indica cómo se muestran las fechas al llamar a la función <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Indica cómo determinar y dar formato a los intervalos de fecha al llamar a las funciones relacionadas con fechas.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Especifica qué se hace cuando un directorio que se va a eliminar contiene archivos o directorios.|  
|<xref:Microsoft.VisualBasic.DueDate>|Indica cuándo vencen los pagos al llamar a métodos financieros.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Indica si los campos de texto están delimitados o son de ancho fijo.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Indica los atributos de archivo que se deben utilizar al llamar a las funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Indica el primer día de la semana que se utiliza al llamar a funciones relacionadas con fechas.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Indica la primera semana del año que se utiliza al llamar a funciones relacionadas con fechas.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Indica en qué botón se hizo clic en un cuadro de mensaje, devuelto por la función <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Indica los botones que se muestran al llamar a la función <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Indica cómo abrir un archivo al llamar a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Indica cómo abrir un archivo al llamar a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Indica cómo abrir un archivo al llamar a funciones de acceso a archivos.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Especifica si se debe eliminar un archivo permanentemente o se debe colocar en la Papelera de reciclaje.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Especifica si se buscan todos o sólo los directorios de nivel superior.|  
|<xref:Microsoft.VisualBasic.TriState>|Indica un valor de tipo `Boolean` o si se debe utilizar el valor predeterminado al llamar a las funciones de formato de números.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Especifica lo que se debe hacer si el usuario hace clic en **Cancelar** durante una operación.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Especifica si se muestra o no un cuadro de diálogo de progreso al copiar, eliminar o mover archivos o directorios.|  
|<xref:Microsoft.VisualBasic.VariantType>|Indica el tipo de un objeto de variante, devuelto por la función <xref:Microsoft.VisualBasic.Information.VarType%2A>.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Indica qué tipo de conversión se debe realizar al llamar a la función <xref:Microsoft.VisualBasic.Strings.StrConv%2A>.|  
  
## Vea también  
 [Referencia del lenguaje Visual Basic](../../visual-basic/language-reference/index.md)   
 [Visual Basic](../../visual-basic/index.md)   
 [Información general sobre las constantes](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Información general sobre las enumeraciones](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)