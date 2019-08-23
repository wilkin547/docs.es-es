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
ms.openlocfilehash: d4afcd6ce942d1cd2286e3f393ce61436821bb3a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955125"
---
# <a name="how-to-add-data-to-the-clipboard"></a>Procedimiento para agregar datos al Portapapeles
La <xref:System.Windows.Forms.Clipboard> clase proporciona métodos que se pueden usar para interactuar con la característica del Portapapeles del sistema operativo Windows. Muchas aplicaciones usan el portapapeles como repositorio temporal para los datos. Por ejemplo, los procesadores de textos utilizan el portapapeles durante las operaciones de cortar y pegar. El portapapeles también es útil para transferir datos de una aplicación a otra.  
  
 Al agregar datos al portapapeles, puede indicar el formato de los datos para que otras aplicaciones puedan reconocer los datos si pueden usar ese formato. También puede agregar datos al portapapeles en varios formatos diferentes para aumentar el número de otras aplicaciones que pueden utilizar potencialmente los datos.  
  
 Un formato de Portapapeles es una cadena que identifica el formato para que una aplicación que utiliza ese formato pueda recuperar los datos asociados. La <xref:System.Windows.Forms.DataFormats> clase proporciona nombres de formato predefinidos para su uso. También puede usar sus propios nombres de formato o usar el tipo de un objeto como formato.  
  
 Para agregar datos al portapapeles en uno o varios formatos, use <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> el método. Puede pasar cualquier objeto a este método, pero para agregar datos en varios formatos, primero debe agregar los datos a un objeto independiente diseñado para trabajar con varios formatos. Normalmente, agregará los datos a un <xref:System.Windows.Forms.DataObject>, pero puede usar cualquier tipo que implemente la <xref:System.Windows.Forms.IDataObject> interfaz.  
  
 En .NET Framework 2,0, puede agregar datos directamente al portapapeles mediante nuevos métodos diseñados para facilitar las tareas básicas del portapapeles. Utilice estos métodos cuando trabaje con datos en un solo formato común, como texto.  
  
> [!NOTE]
> Todas las aplicaciones basadas en Windows comparten el portapapeles. Por lo tanto, el contenido está sujeto a cambios al cambiar a otra aplicación.  
>   
>  La <xref:System.Windows.Forms.Clipboard> clase solo se puede usar en los subprocesos establecidos en el modo de contenedor uniproceso (STA). Para usar esta clase, asegúrese de que `Main` el método está marcado con <xref:System.STAThreadAttribute> el atributo.  
>   
>  Un objeto debe ser serializable para que se pueda colocar en el portapapeles. Para convertir un tipo en serializable, márquelo con el <xref:System.SerializableAttribute> atributo. Si pasa un objeto no serializable a un método Clipboard, se producirá un error en el método sin producir una excepción. Para obtener más información acerca de la serialización, vea <xref:System.Runtime.Serialization>.  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>Para agregar datos al portapapeles en un único formato común  
  
1. Use el <xref:System.Windows.Forms.Clipboard.SetAudio%2A>método <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, o <xref:System.Windows.Forms.Clipboard.SetText%2A> . Estos métodos solo están disponibles en .NET Framework 2,0.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>Para agregar datos al portapapeles en un formato personalizado  
  
1. Use el <xref:System.Windows.Forms.Clipboard.SetData%2A> método con un nombre de formato personalizado. Este método solo está disponible en .NET Framework 2,0.  
  
     También puede utilizar nombres de formato predefinidos con <xref:System.Windows.Forms.Clipboard.SetData%2A> el método. Para obtener más información, consulta <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>Para agregar datos al portapapeles en varios formatos  
  
1. Use el <xref:System.Windows.Forms.Clipboard.SetDataObject%2A?displayProperty=nameWithType> método y pase un <xref:System.Windows.Forms.DataObject> que contenga los datos. Debe utilizar este método para agregar datos al portapapeles en versiones anteriores a .NET Framework 2,0.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Vea también

- [Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles](drag-and-drop-operations-and-clipboard-support.md)
- [Procedimientos: Recuperar datos del portapapeles](how-to-retrieve-data-from-the-clipboard.md)
