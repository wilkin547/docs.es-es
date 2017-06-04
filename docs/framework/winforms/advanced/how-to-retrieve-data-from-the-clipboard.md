---
title: "How to: Retrieve Data from the Clipboard | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "pasting Clipboard data"
  - "Clipboard, retrieving data"
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Retrieve Data from the Clipboard
La clase <xref:System.Windows.Forms.Clipboard> proporciona métodos que puede utilizar para interactuar con la característica Portapapeles del sistema operativo Windows.  Muchas aplicaciones utilizan el Portapapeles como un repositorio temporal para los datos.  Por ejemplo, los procesadores de textos utilizan el Portapapeles durante las operaciones de cortar y pegar.  El Portapapeles también resulta de utilidad para transferir información de una aplicación a otra.  
  
 Algunas aplicaciones almacenan datos en el Portapapeles en varios formatos para aumentar el número de otras aplicaciones que pueden utilizar potencialmente los datos.  Un formato de Portapapeles es una cadena que identifica el formato.  Una aplicación que utiliza el formato identificado puede recuperar los datos asociados en el Portapapeles.  La clase <xref:System.Windows.Forms.DataFormats> proporciona los nombres de formato predefinidos para su uso.  También puede utilizar sus propios nombres de formato o utilizar un tipo de objeto como su formato.  Para obtener información sobre cómo agregar datos al Portapapeles, vea [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md).  
  
 Para determinar si el Portapapeles contiene datos en un formato determinado, utilice uno de los métodos `Contains`*Formato* o el método <xref:System.Windows.Forms.Clipboard.GetData%2A>.  Para recuperar datos del Portapapeles, utilice uno de los métodos `Get`*Formato* o el método <xref:System.Windows.Forms.Clipboard.GetData%2A>.  Estos métodos son nuevos en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
 Para tener acceso a los datos del Portapapeles utilizando versiones anteriores a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], utilice el método <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> y llame a los métodos de la interfaz <xref:System.Windows.Forms.IDataObject> devuelta.  Para determinar si un formato determinado está disponible en el objeto devuelto, por ejemplo, llame al método <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A>.  
  
> [!NOTE]
>  Todas las aplicaciones basadas en Windows comparten el Portapapeles del sistema.  Por consiguiente, el contenido está sujeto a cambios cuando pase a otra aplicación.  
>   
>  La clase <xref:System.Windows.Forms.Clipboard> sólo se puede utilizar en subprocesos establecidos en modo STA \(Subprocesamiento controlado simple\).  Para utilizar esta clase, cerciórese de que el método `Main` está marcado con el atributo <xref:System.STAThreadAttribute>.  
  
### Para recuperar datos del Portapapeles en un solo formato común  
  
1.  Utilice el método <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A> o <xref:System.Windows.Forms.Clipboard.GetText%2A>.  Opcionalmente, utilice primero los métodos `Contains`*Formato* correspondientes para determinar si los datos están disponibles en un formato determinado.  Estos métodos sólo están disponibles en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### Para recuperar datos del Portapapeles en un formato personalizado  
  
1.  Utilice el método <xref:System.Windows.Forms.Clipboard.GetData%2A> con un nombre de formato personalizado.  Este método sólo está disponible en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     También puede utilizar los nombres de formato predefinidos con el método <xref:System.Windows.Forms.Clipboard.SetData%2A>.  Para obtener más información, vea <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### Para recuperar datos del Portapapeles en varios formatos  
  
1.  Utilice el método <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>.  Debe utilizar este método para recuperar datos del Portapapeles en versiones anteriores a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## Vea también  
 [Drag\-and\-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)   
 [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)