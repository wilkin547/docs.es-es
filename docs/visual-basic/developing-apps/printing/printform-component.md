---
title: El componente PrintForm (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic]
ms.assetid: 03de98b8-b54c-4764-91d7-83c64e974750
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f0c51ef0131c874ed33af7a19f9145a790d14ade
ms.lasthandoff: 03/13/2017

---
# <a name="printform-component-visual-basic"></a>PrintForm (componente, Visual Basic)
El <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] permite imprimir una imagen de un formulario Windows Forms en tiempo de ejecución.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Su comportamiento reemplaza el del método `PrintForm` en versiones anteriores de Visual Basic.  
  
 Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [Centro de descarga](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
## <a name="printform-component-overview"></a>Información general del componente PrintForm  
 Un escenario común de Windows Forms consiste en crear un formulario formateado para que se parezca a un formulario en papel o un informe y, después, imprimir una imagen de dicho formulario. Aunque puede usar un <xref:System.Drawing.Printing.PrintDocument>componente para hacer esto, requeriría mucho código.</xref:System.Drawing.Printing.PrintDocument> El <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente permite imprimir una imagen de un formulario a una impresora, a una ventana de vista previa de impresión o a un archivo sin utilizar un <xref:System.Drawing.Printing.PrintDocument>componente.</xref:System.Drawing.Printing.PrintDocument> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 El <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente se encuentra en la **Visual Basic PowerPacks** ficha de la **cuadro de herramientas**.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Cuando se arrastra a un formulario, aparece en la bandeja de componentes, la pequeña área debajo del borde inferior del formulario. Cuando se selecciona el componente, se pueden establecer las propiedades que definen su comportamiento en la ventana **Propiedades** . Todas estas propiedades también pueden establecerse en el código. También puede crear una instancia de la <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente en el código sin agregar el componente en tiempo de diseño.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 Al imprimir un formulario, se imprime todo el contenido del área de cliente. Se incluyen todos los controles y el texto o los gráficos dibujados en el formulario mediante métodos gráficos. De forma predeterminada, no se imprimen la barra de título, las barras de desplazamiento ni el borde del formulario. También de forma predeterminada, la <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente imprime sólo la parte visible del formulario.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Por ejemplo, si el usuario cambia el tamaño del formulario en tiempo de ejecución, se imprimen los controles y los gráficos que son visibles actualmente.  
  
 La impresora predeterminada utilizada por la <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente viene determinado por la configuración del Panel de Control del sistema operativo.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 Una vez iniciada la impresión, un estándar <xref:System.Drawing.Printing.PrintDocument>se muestra el cuadro de diálogo Imprimir.</xref:System.Drawing.Printing.PrintDocument> Este cuadro de diálogo permite a los usuarios cancelar el trabajo de impresión.  
  
### <a name="key-methods-properties-and-events"></a>Métodos, propiedades y eventos clave  
 El método clave de la <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente es el <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>método, que imprime una imagen del formulario a una impresora, la ventana de vista previa de impresión o el archivo.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Hay dos versiones de la <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>método:</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
  
-   Una versión básica sin parámetros:`Print()`  
  
-   Una versión sobrecargada con parámetros que especifican el comportamiento de impresión:`Print(printForm As Form, printFormOption As PrintOption)`  
  
     El parámetro `PrintOption` del método sobrecargado determina la implementación subyacente que se usa para imprimir el formulario, y si deben imprimirse la barra de título, las barras de desplazamiento y el borde del formulario, así como sus partes desplazables.  
  
 El <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>propiedad es una propiedad clave de la <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> Esta propiedad determina si el resultado se envía a una impresora, se muestra en una ventana de vista previa de impresión o se guarda como un archivo PostScript encapsulado. Si el <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>propiedad se establece en <xref:System.Drawing.Printing.PrintAction>, el <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>propiedad especifica la ruta de acceso y nombre de archivo.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> </xref:System.Drawing.Printing.PrintAction> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
  
 La <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A>propiedad proporciona acceso a un subyacente <xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A>objeto que le permite especificar parámetros como la impresora que utilice y el número de copias para imprimir.</xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A> También puede consultar las capacidades de la impresora, como el color o la compatibilidad con dúplex. Esta propiedad no aparece en la ventana **Propiedades** ; solo es accesible desde el código.  
  
 El <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A>propiedad se utiliza para especificar el formato para imprimir al invocar el <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente mediante programación.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A> Si el componente se agrega a un formulario en tiempo de diseño, dicho formulario será el predeterminado.  
  
 La clave de eventos para el <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente incluyen los siguientes:</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint>evento.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint> Se produce cuando el <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>se llama al método y antes de la primera página de imprimir el documento.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint>evento.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint> Se produce después de la impresión de la última página.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings>evento.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings> Se produce inmediatamente antes de que se imprima cada página.  
  
### <a name="remarks"></a>Comentarios  
 Si un formulario contiene texto o gráficos que se dibujan <xref:System.Drawing.Graphics>métodos, use el basic <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>(`Print()`) método imprímalo.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> </xref:System.Drawing.Graphics> No pueden representar gráficos en algunos sistemas operativos cuando sobrecargado <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>método sirve.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
  
 Si el ancho de un formulario es mayor que el ancho del papel de la impresora, el lado derecho del formulario podría cortarse. Al diseñar formularios para impresión, asegúrese de que el formulario quepa en papel de tamaño estándar.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un uso común de la <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
```  
' Visual Basic.  
Dim pf As New PrintForm  
pf.Form = Me  
pf.PrintAction = PrintToPrinter  
pf.Print()  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A></xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A></xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>   
 [Cómo: imprimir un formulario mediante el componente PrintForm](../../../visual-basic/developing-apps/printing/how-to-print-a-form-by-using-the-printform-component.md)   
 [Cómo: imprimir el área de cliente de un formulario](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)   
 [Cómo: imprimir áreas no cliente de un formulario y](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)   
 [Imprimir un formulario desplazable](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
