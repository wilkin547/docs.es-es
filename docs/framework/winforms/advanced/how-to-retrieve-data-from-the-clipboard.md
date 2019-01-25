---
title: Procedimiento Recuperar datos del Portapapeles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
ms.openlocfilehash: 8857ebb5a5c29f8e945ea47c290259c4b787b430
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545717"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>Procedimiento Recuperar datos del Portapapeles
La <xref:System.Windows.Forms.Clipboard> clase proporciona métodos que puede usar para interactuar con la función de Portapapeles del sistema operativo Windows. Muchas aplicaciones utilizan el Portapapeles como un repositorio temporal para los datos. Por ejemplo, procesadores de textos utilizan el Portapapeles durante las operaciones de cortar y pegar. El Portapapeles también es útil para transferir información desde una aplicación a otra.  
  
 Algunas aplicaciones almacenan datos en el Portapapeles con varios formatos para aumentar el número de otras aplicaciones que pueden utilizar potencialmente los datos. Un formato de Portapapeles es una cadena que identifica el formato. Una aplicación que utiliza el formato identificado puede recuperar los datos asociados en el Portapapeles. La <xref:System.Windows.Forms.DataFormats> clase proporciona los nombres de formato predefinidos para su uso. También puede utilizar sus propios nombres de formato o usar un tipo de objeto como su formato. Para obtener información acerca de cómo agregar datos al Portapapeles, vea [Cómo: Agregar datos al Portapapeles](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md).  
  
 Para determinar si el Portapapeles contiene datos en un formato determinado, utilice uno de los `Contains` *formato* métodos o <xref:System.Windows.Forms.Clipboard.GetData%2A> método. Para recuperar datos desde el Portapapeles, utilice uno de los `Get` *formato* métodos o <xref:System.Windows.Forms.Clipboard.GetData%2A> método. Estos métodos son nuevos en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
 Acceso a los datos del Portapapeles con versiones anteriores a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], utilice el <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> método y llamar a los métodos de devuelto <xref:System.Windows.Forms.IDataObject>. Para determinar si un formato determinado está disponible en el objeto devuelto, por ejemplo, llamar a la <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> método.  
  
> [!NOTE]
>  Todas las aplicaciones basadas en Windows comparten el Portapapeles del sistema. Por lo tanto, el contenido está sujeta a cambios cuando se cambia a otra aplicación.  
>   
>  La <xref:System.Windows.Forms.Clipboard> clase solo puede usarse en subprocesos establecidos en modo de apartamento de un único subproceso. Para usar esta clase, asegúrese de que su `Main` método está marcado con el <xref:System.STAThreadAttribute> atributo.  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>Para recuperar datos del Portapapeles en un solo formato común  
  
1.  Use la <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, o <xref:System.Windows.Forms.Clipboard.GetText%2A> método. Opcionalmente, use el correspondiente `Contains` *formato* métodos primero para determinar si los datos están disponibles en un formato determinado. Estos métodos solo están disponibles en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>Para recuperar datos del Portapapeles en un formato personalizado  
  
1.  Use el <xref:System.Windows.Forms.Clipboard.GetData%2A> método con un nombre de formato personalizado. Este método solo está disponible en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     También puede usar nombres de formato predefinidos con el <xref:System.Windows.Forms.Clipboard.SetData%2A> método. Para obtener más información, consulta <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>Para recuperar datos del Portapapeles en varios formatos  
  
1.  Utilice el método <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>. Debe usar este método para recuperar datos del Portapapeles en las versiones anteriores a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Vea también
- [Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)
- [Cómo: Agregar datos al Portapapeles](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)
