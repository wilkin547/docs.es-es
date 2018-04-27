---
title: PrintForm (componente, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- PrintForm component [Visual Basic]
ms.assetid: 03de98b8-b54c-4764-91d7-83c64e974750
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3269a980d19466205e6c67a18f22dded9301ec59
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="printform-component-visual-basic"></a>PrintForm (componente, Visual Basic)
El <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> componente de Visual Basic permite imprimir una imagen de un formulario Windows Forms en tiempo de ejecución. Su comportamiento reemplaza el del método `PrintForm` en versiones anteriores de Visual Basic.  
  
 Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [Centro de descarga](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
## <a name="printform-component-overview"></a>Información general del componente PrintForm  
 Un escenario común de Windows Forms consiste en crear un formulario formateado para que se parezca a un formulario en papel o un informe y, después, imprimir una imagen de dicho formulario. Aunque puede usar un componente <xref:System.Drawing.Printing.PrintDocument> para hacerlo, se necesitaría una gran cantidad de código. El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> permite imprimir una imagen de un formulario en una impresora, en una ventana de vista previa de impresión o en un archivo sin usar un componente <xref:System.Drawing.Printing.PrintDocument> .  
  
 El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se encuentra en la pestaña **Visual Basic PowerPacks** del **Cuadro de herramientas**. Cuando se arrastra a un formulario, aparece en la bandeja de componentes, la pequeña área debajo del borde inferior del formulario. Cuando se selecciona el componente, se pueden establecer las propiedades que definen su comportamiento en la ventana **Propiedades** . Todas estas propiedades también pueden establecerse en el código. También puede crear una instancia del componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> en el código sin agregar el componente en tiempo de diseño.  
  
 Al imprimir un formulario, se imprime todo el contenido del área de cliente. Se incluyen todos los controles y el texto o los gráficos dibujados en el formulario mediante métodos gráficos. De forma predeterminada, no se imprimen la barra de título, las barras de desplazamiento ni el borde del formulario. También de forma predeterminada, el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> imprime solo la parte visible del formulario. Por ejemplo, si el usuario cambia el tamaño del formulario en tiempo de ejecución, se imprimen los controles y los gráficos que son visibles actualmente.  
  
 La impresora predeterminada usada por el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> viene determinada por la configuración del Panel de Control del sistema operativo.  
  
 Una vez iniciada la impresión, se muestra un cuadro de diálogo de impresión <xref:System.Drawing.Printing.PrintDocument> estándar. Este cuadro de diálogo permite a los usuarios cancelar el trabajo de impresión.  
  
### <a name="key-methods-properties-and-events"></a>Métodos, propiedades y eventos clave  
 El método clave del componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> es el método <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> , que imprime una imagen del formulario en una impresora, una ventana de vista previa de impresión o un archivo. Existen dos versiones del método <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> :  
  
-   Una versión básica sin parámetros: `Print()`  
  
-   Una versión sobrecargada con parámetros que especifican el comportamiento de la impresión: `Print(printForm As Form, printFormOption As PrintOption)`  
  
     El parámetro `PrintOption` del método sobrecargado determina la implementación subyacente que se usa para imprimir el formulario, y si deben imprimirse la barra de título, las barras de desplazamiento y el borde del formulario, así como sus partes desplazables.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> es una propiedad clave del componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> . Esta propiedad determina si el resultado se envía a una impresora, se muestra en una ventana de vista previa de impresión o se guarda como un archivo PostScript encapsulado. Si la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> se establece en <xref:System.Drawing.Printing.PrintAction.PrintToFile>, la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> especifica la ruta de acceso y nombre de archivo.  
  
 La propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A> proporciona acceso a un objeto <xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A> subyacente que le permite especificar estas opciones de configuración, como la impresora que quiere usar y el número de copias que desea imprimir. También puede consultar la funcionalidad de la impresora, como el color o la compatibilidad con dúplex. Esta propiedad no aparece en la ventana **Propiedades** ; solo es accesible desde el código.  
  
 La propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A> se usa para especificar el formulario que se va a imprimir al invocar el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> mediante programación. Si el componente se agrega a un formulario en tiempo de diseño, dicho formulario será el predeterminado.  
  
 Algunos eventos clave del componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> son:  
  
-   Evento<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint> . Se produce cuando se llama al método <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> antes de que se imprima la primera página del documento.  
  
-   Evento<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint> . Se produce después de la impresión de la última página.  
  
-   Evento<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings> . Se produce inmediatamente antes de que se imprima cada página.  
  
### <a name="remarks"></a>Comentarios  
 Si un formulario contiene texto o gráficos dibujados por métodos <xref:System.Drawing.Graphics> , use el método <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> básico (`Print()`) para imprimirlo. Es posible que los gráficos no se representen en algunos sistemas operativos si se usa el método <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> sobrecargado.  
  
 Si el ancho de un formulario es mayor que el ancho del papel de la impresora, el lado derecho del formulario podría cortarse. Al diseñar formularios para impresión, asegúrese de que el formulario quepa en papel de tamaño estándar.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un uso común del componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> .  
  
```  
' Visual Basic.  
Dim pf As New PrintForm  
pf.Form = Me  
pf.PrintAction = PrintToPrinter  
pf.Print()  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 [Imprimir un formulario mediante el componente PrintForm](../../../visual-basic/developing-apps/printing/how-to-print-a-form-by-using-the-printform-component.md)  
 [Imprimir el área de cliente de un formulario](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [Imprimir áreas de cliente y áreas que no son de cliente de un formulario](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [Imprimir un formulario desplazable](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
