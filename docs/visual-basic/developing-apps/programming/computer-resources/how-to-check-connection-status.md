---
title: "C&#243;mo: Comprobar el estado de conexi&#243;n en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "estado de conexiones"
  - "conexiones, comprobar el estado"
  - "IsAvailable (propiedad), acerca de IsAvailable"
  - "conexiones Web"
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# C&#243;mo: Comprobar el estado de conexi&#243;n en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La propiedad <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> se puede utilizar para determinar si el equipo tiene una red activa o conexión a Internet.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Para comprobar si un equipo tiene una conexión de red activa  
  
-   Determine si la propiedad `IsAvailable` es `True` o `False`.  El código siguiente comprueba el estado de la propiedad e informa de él:  
  
     [!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]  
  
     Este ejemplo de código también está disponible como fragmento de código de IntelliSense.  En el selector de fragmentos de código, se encuentra en **Conectividad y redes**.  Para obtener más información, vea [Fragmentos de código](/visual-studio/ide/code-snippets).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>