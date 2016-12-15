---
title: "Obtener informaci&#243;n sobre el equipo (Visual Basic) | Microsoft Docs"
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
  - "My.Computer.Info (objeto), tareas"
ms.assetid: 13c145bc-5c85-4fea-a5dd-2ca8681a0252
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Obtener informaci&#243;n sobre el equipo (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El objeto `My.Computer.Info` proporciona propiedades para obtener información sobre la memoria, los ensamblados cargados, el nombre y el sistema operativo del equipo.  
  
## Comentarios  
 Esta tabla enumera las tareas que se realizan normalmente mediante el objeto `My.Computer.Info` y señala a temas que muestran cómo llevar a cabo cada una de ellas.  
  
|||  
|-|-|  
|Para|Vea|  
|Determinar cuánto espacio de la dirección virtual está disponible para el equipo en el que se instala la aplicación|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.TotalVirtualMemory%2A>|  
|Determinar el tipo de plataforma del equipo en el que se está ejecutando la aplicación|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSPlatform%2A>|  
|Determinar el sistema operativo del equipo en el que se está ejecutando la aplicación|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName%2A>|  
|Determinar qué Service Pack se ha instalado en el equipo en el que se está ejecutando la aplicación|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSVersion%2A>|  
|Determinar la `UICulture` instalada en el equipo en el que se está ejecutando la aplicación|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.InstalledUICulture%2A>|  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>