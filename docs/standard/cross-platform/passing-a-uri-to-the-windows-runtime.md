---
title: "Pasar un URI a Windows Runtime | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Windows Runtime, compatibilidad de .NET Framework con"
  - "Windows Runtime, pasar un URI a"
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Pasar un URI a Windows Runtime
Los métodos de Windows Runtime solo aceptan URI absolutos. Si se pasa un URI relativo a un método [!INCLUDE[wrt](../../../includes/wrt-md.md)], se produce una excepción <xref:System.ArgumentException>. El motivo es el siguiente: cuando se usa [!INCLUDE[wrt](../../../includes/wrt-md.md)] en el código de .NET Framework, la clase [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) aparece como <xref:System.Uri?displayProperty=fullName> en Intellisense. La clase <xref:System.Uri?displayProperty=fullName> permite URI relativos, pero la clase [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) no. Esto también ocurre con los métodos que usted expone en componentes de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Si su componente expone un método que toma un URI, la firma de su código incluye <xref:System.Uri?displayProperty=fullName>. Sin embargo, para los usuarios del componente, la firma incluye [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376). Un URI que se pase a su componente debe ser absoluto.  
  
 En este tema se muestra cómo detectar un URI absoluto y cómo crear uno al hacer referencia a un recurso del paquete de la aplicación.  
  
## Detectar y usar un URI absoluto  
 Use la propiedad <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=fullName> para asegurarse de que un URI sea absoluto antes de pasarlo a [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Utilizar esta propiedad es más eficaz que detectar y gestionar la excepción <xref:System.ArgumentException>.  
  
## Usar un URI absoluto para un recurso del paquete de la aplicación  
 Si desea especificar un URI para un recurso incluido en el paquete de la aplicación, puede usar los esquemas `ms-appx` o `ms-appx-web` para crear un URI absoluto.  
  
 En el ejemplo siguiente se muestra cómo establecer la propiedad [Source](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) de un control [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) y la propiedad [Source](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) de un control [Image](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) en recursos incluidos en una carpeta denominada "Pages", usando para ello XAML y código.  
  
 [!code-xml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 Para obtener más información sobre estos esquemas, consulte [Esquemas de URI](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) en el Centro de desarrollo de Windows.  
  
## Vea también  
 [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)