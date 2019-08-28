---
title: Procedimiento para recuperar datos del Portapapeles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
ms.openlocfilehash: ca24615049abcc145698c033f31e6c98a38253bf
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040565"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>Procedimiento para recuperar datos del Portapapeles

La <xref:System.Windows.Forms.Clipboard> clase proporciona métodos que se pueden usar para interactuar con la característica del Portapapeles del sistema operativo Windows. Muchas aplicaciones usan el portapapeles como repositorio temporal para los datos. Por ejemplo, los procesadores de textos utilizan el portapapeles durante las operaciones de cortar y pegar. El portapapeles también es útil para transferir información de una aplicación a otra.

Algunas aplicaciones almacenan datos en el portapapeles en varios formatos para aumentar el número de otras aplicaciones que pueden utilizar potencialmente los datos. Un formato de Portapapeles es una cadena que identifica el formato. Una aplicación que utiliza el formato identificado puede recuperar los datos asociados en el portapapeles. La <xref:System.Windows.Forms.DataFormats> clase proporciona nombres de formato predefinidos para su uso. También puede usar sus propios nombres de formato o usar el tipo de un objeto como formato. Para obtener información sobre cómo agregar datos al portapapeles, vea [cómo: Agregar datos al portapapeles](how-to-add-data-to-the-clipboard.md).

Para determinar si el Portapapeles contiene datos en un formato determinado, use uno `Contains`de los métodos de <xref:System.Windows.Forms.Clipboard.GetData%2A> *formato* o el método. Para recuperar datos del portapapeles, use uno de `Get`los métodos de *formato* o el <xref:System.Windows.Forms.Clipboard.GetData%2A> método. Estos métodos son nuevos en .NET Framework 2,0.

Para obtener acceso a los datos del Portapapeles con versiones anteriores a .NET Framework 2,0 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A?displayProperty=nameWithType> , use el método y llame a los <xref:System.Windows.Forms.IDataObject>métodos del devuelto. Para determinar si un formato determinado está disponible en el objeto devuelto, por ejemplo, llame <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> al método.

> [!NOTE]
> Todas las aplicaciones basadas en Windows comparten el Portapapeles del sistema. Por lo tanto, el contenido está sujeto a cambios al cambiar a otra aplicación.
>
> La <xref:System.Windows.Forms.Clipboard> clase solo se puede usar en los subprocesos establecidos en el modo de contenedor uniproceso (STA). Para usar esta clase, asegúrese de que `Main` el método está marcado con <xref:System.STAThreadAttribute> el atributo.

### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>Para recuperar datos del portapapeles en un formato común único

1. Use el <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>método <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, o <xref:System.Windows.Forms.Clipboard.GetText%2A> . Opcionalmente, utilice primero los `Contains`métodos de *formato* correspondientes para determinar si los datos están disponibles en un formato determinado. Estos métodos solo están disponibles en .NET Framework 2,0.

    [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
    [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]

### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>Para recuperar datos del portapapeles en un formato personalizado

1. Use el <xref:System.Windows.Forms.Clipboard.GetData%2A> método con un nombre de formato personalizado. Este método solo está disponible en .NET Framework 2,0.

    También puede utilizar nombres de formato predefinidos con <xref:System.Windows.Forms.Clipboard.SetData%2A> el método. Para obtener más información, consulta <xref:System.Windows.Forms.DataFormats>.

    [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
    [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>Para recuperar datos del portapapeles en varios formatos

1. Utilice el método <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>. Debe utilizar este método para recuperar datos del portapapeles en versiones anteriores a .NET Framework 2,0.

    [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
    [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

## <a name="see-also"></a>Vea también

- [Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles](drag-and-drop-operations-and-clipboard-support.md)
- [Cómo: Agregar datos al portapapeles](how-to-add-data-to-the-clipboard.md)
