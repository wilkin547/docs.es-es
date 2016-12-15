---
title: "Acceso a los datos de usuario (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "datos [Visual Basic], obtener acceso a los datos del usuario"
  - "nombres de dominio, recuperar"
  - "ejemplos [Visual Basic], obtener acceso a los datos del usuario"
  - "nombres de inicio de sesión"
  - "My.User (objeto), tareas"
  - "datos del usuario, obtener acceso"
  - "datos del usuario, dominio"
  - "nombres de usuario, recuperar"
ms.assetid: 32492a15-ee59-4a63-a1f1-9b24cc13140a
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Acceso a los datos de usuario (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Esta sección contiene temas que tratan del objeto `My.User` y las tareas que se pueden realizar con él.  
  
 El objeto `My.User` proporciona acceso a información sobre el usuario que ha iniciado la sesión devolviendo un objeto que implementa la interfaz <xref:System.Security.Principal.IPrincipal>.  
  
## Tareas  
  
|Para|Vea|  
|----------|---------|  
|Obtener el nombre de inicio de sesión del usuario.|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|Obtener el nombre de dominio del usuario si la aplicación utiliza la autenticación de Windows.|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|Determinar el rol del usuario|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>