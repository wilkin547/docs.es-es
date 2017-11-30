---
title: "Cómo: obtener todas las ventanas en una aplicación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8577817f62ece1465f9c7577f3e1b7ff5ecefe44
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-get-all-windows-in-an-application"></a>Cómo: obtener todas las ventanas en una aplicación
Este ejemplo muestra cómo obtener todos los <xref:System.Windows.Window> objetos en una aplicación.  
  
## <a name="example"></a>Ejemplo  
 Cada crea una instancia <xref:System.Windows.Window> objeto, si es visible o no, se agrega automáticamente a una colección de referencias de ventana que está administrado por <xref:System.Windows.Application>y está expuesto desde <xref:System.Windows.Application.Windows%2A>.  
  
 Puede enumerar <xref:System.Windows.Application.Windows%2A> para obtener todas las instancias de windows con el código siguiente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
