---
title: Procedimiento para agregar datos al Portapapeles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
ms.openlocfilehash: 06ce64de5e2a6b4aa299b9ad9c41982b7c1924c7
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348277"
---
# <a name="how-to-add-data-to-the-clipboard"></a>Procedimiento para agregar datos al Portapapeles
La <xref:System.Windows.Forms.Clipboard> clase proporciona métodos que puede usar para interactuar con la función de Portapapeles del sistema operativo Windows. Muchas aplicaciones utilizan el Portapapeles como un repositorio temporal para los datos. Por ejemplo, procesadores de textos utilizan el Portapapeles durante las operaciones de cortar y pegar. El Portapapeles también es útil para transferir datos desde una aplicación a otra.  
  
 Al agregar datos en el Portapapeles, puede indicar el formato de datos para que otras aplicaciones pueden reconocer los datos si puede usar ese formato. También puede agregar datos al Portapapeles en varios formatos diferentes para aumentar el número de otras aplicaciones que pueden utilizar potencialmente los datos.  
  
 Un formato de Portapapeles es una cadena que identifica el formato para que una aplicación que utiliza ese formato puedan recuperar los datos asociados. La <xref:System.Windows.Forms.DataFormats> clase proporciona los nombres de formato predefinidos para su uso. También puede utilizar sus propios nombres de formato o usar el tipo de un objeto como su formato.  
  
 Para agregar datos al Portapapeles en uno o varios formatos, utilice el <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> método. Puede pasar cualquier objeto a este método, pero para agregar datos en varios formatos, debe agregar primero los datos a un objeto independiente diseñado para trabajar con varios formatos. Normalmente, agregará los datos a un <xref:System.Windows.Forms.DataObject>, pero puede usar cualquier tipo que implementa el <xref:System.Windows.Forms.IDataObject> interfaz.  
  
 En .NET Framework 2.0, puede agregar datos directamente en el Portapapeles con nuevos métodos diseñados para facilitar las tareas básicas del Portapapeles. Utilice estos métodos cuando se trabaja con datos en un único formato común, como texto.  
  
> [!NOTE]
>  Todas las aplicaciones basadas en Windows comparten el Portapapeles. Por lo tanto, el contenido está sujeta a cambios cuando se cambia a otra aplicación.  
>   
>  La <xref:System.Windows.Forms.Clipboard> clase solo puede usarse en subprocesos establecidos en modo de apartamento de un único subproceso. Para usar esta clase, asegúrese de que su `Main` método está marcado con el <xref:System.STAThreadAttribute> atributo.  
>   
>  Un objeto debe ser serializable para que se pueda colocar en el Portapapeles. Para hacer que un tipo serializable, márquelo con el <xref:System.SerializableAttribute> atributo. Si se pasa un objeto no serializable a un método de Portapapeles, se producirá un error en el método sin producir una excepción. Para obtener más información acerca de la serialización, vea <xref:System.Runtime.Serialization>.  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>Para agregar datos al Portapapeles en un solo formato común  
  
1. Use la <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, o <xref:System.Windows.Forms.Clipboard.SetText%2A> método. Estos métodos solo están disponibles en .NET Framework 2.0.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>Para agregar datos al Portapapeles en un formato personalizado  
  
1. Use el <xref:System.Windows.Forms.Clipboard.SetData%2A> método con un nombre de formato personalizado. Este método solo está disponible en .NET Framework 2.0.  
  
     También puede usar nombres de formato predefinidos con el <xref:System.Windows.Forms.Clipboard.SetData%2A> método. Para obtener más información, consulta <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>Para agregar datos al Portapapeles en varios formatos  
  
1. Use la <xref:System.Windows.Forms.Clipboard.SetDataObject%2A?displayProperty=nameWithType> método y pase un <xref:System.Windows.Forms.DataObject> que contiene los datos. Debe usar este método para agregar datos en el Portapapeles en versiones anteriores a .NET Framework 2.0.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Vea también

- [Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles](drag-and-drop-operations-and-clipboard-support.md)
- [Cómo: Recuperar datos del Portapapeles](how-to-retrieve-data-from-the-clipboard.md)
