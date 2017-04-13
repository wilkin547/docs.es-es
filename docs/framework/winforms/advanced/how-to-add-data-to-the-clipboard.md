---
title: "How to: Add Data to the Clipboard | Microsoft Docs"
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
  - "Clipboard, copying data to"
  - "data [Windows Forms], copying to Clipboard"
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# How to: Add Data to the Clipboard
La clase <xref:System.Windows.Forms.Clipboard> proporciona métodos que puede utilizar para interactuar con la característica Portapapeles del sistema operativo Windows.  Muchas aplicaciones utilizan el Portapapeles como un repositorio temporal para los datos.  Por ejemplo, los procesadores de textos utilizan el Portapapeles durante las operaciones de cortar y pegar.  El Portapapeles también resulta de utilidad para transferir datos de una aplicación a otra.  
  
 Cuando agrega datos al Portapapeles, puede indicar su formato para que otras aplicaciones los reconozcan si pueden utilizar el formato.  También puede agregar datos al Portapapeles en varios formatos distintos para aumentar el número de otras aplicaciones que pueden utilizar potencialmente los datos.  
  
 Un formato del Portapapeles es una cadena que identifica el formato para que una aplicación que lo utilice pueda recuperar los datos asociados.  La clase <xref:System.Windows.Forms.DataFormats> proporciona los nombres de formato predefinidos para su uso.  También puede utilizar sus propios nombres de formato o un tipo de objeto como su formato.  
  
 Para agregar datos al Portapapeles en uno o varios formatos, utilice el método <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>.  Puede pasar cualquier objeto a este método, pero para agregar datos en varios formatos, antes debe agregar los datos a un objeto independiente diseñado para trabajar con varios formatos.  Normalmente, agregará los datos a <xref:System.Windows.Forms.DataObject>, pero puede utilizar cualquier tipo que implementa la interfaz <xref:System.Windows.Forms.IDataObject>.  
  
 En [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], puede agregar directamente los datos al Portapapeles utilizando los nuevos métodos diseñados para hacer más sencillas las tareas básicas del Portapapeles.  Utilice estos métodos al trabajar con datos en un solo formato común, por ejemplo texto.  
  
> [!NOTE]
>  Todas las aplicaciones basadas en Windows comparten el Portapapeles.  Por consiguiente, el contenido está sujeto a cambios cuando pase a otra aplicación.  
>   
>  La clase <xref:System.Windows.Forms.Clipboard> sólo se puede utilizar en subprocesos establecidos en modo STA \(Subprocesamiento controlado simple\).  Para utilizar esta clase, cerciórese de que el método `Main` está marcado con el atributo <xref:System.STAThreadAttribute>.  
>   
>  Un objeto debe ser serializable para que pueda situarse en el Portapapeles.  Para hacer que un tipo sea serializable, márquelo con el atributo <xref:System.SerializableAttribute>.  Si pasa un objeto no serializable a un método Clipboard, se producirá un error en el método y no se iniciará una excepción.  Para obtener más información sobre serialización, vea <xref:System.Runtime.Serialization>.  
  
### Para agregar datos en el Portapapeles en un solo formato común  
  
1.  Utilice el método <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A> o <xref:System.Windows.Forms.Clipboard.SetText%2A>.  Estos métodos sólo están disponibles en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### Para agregar datos al Portapapeles en un formato personalizado  
  
1.  Utilice el método <xref:System.Windows.Forms.Clipboard.SetData%2A> con un nombre de formato personalizado.  Este método sólo está disponible en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     También puede utilizar los nombres de formato predefinidos con el método <xref:System.Windows.Forms.Clipboard.SetData%2A>.  Para obtener más información, vea <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### Para agregar datos al Portapapeles en varios formatos  
  
1.  Utilice el método <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> y pase una clase <xref:System.Windows.Forms.DataObject> que contiene los datos.  Debe utilizar este método para agregar datos al Portapapeles en versiones anteriores a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## Vea también  
 [Drag\-and\-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)   
 [How to: Retrieve Data from the Clipboard](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)