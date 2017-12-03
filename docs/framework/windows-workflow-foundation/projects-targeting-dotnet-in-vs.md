---
title: Escribir proyectos destinados a .NET Framework 3.0 y 3.5 en Visual Studio 2010
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6dc6657bad5cc11eaa723c733319673468749b79
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="writing-projects-targeting-the-net-framework-30-and-35-in-visual-studio-2010"></a>Escribir proyectos destinados a .NET Framework 3.0 y 3.5 en Visual Studio 2010
Puede utilizar [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] para crear proyectos para [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] versión 3.0 o 3.5. En este tema se describe cómo hacerlo.  
  
> [!NOTE]
>  Al agregar actividades, asegúrese de que se establece la versión deseada de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Cambiar la versión de destino del flujo de trabajo una vez agregadas las actividades producirá un error de validación en el flujo de trabajo.  
  
> [!WARNING]
>  Abrir flujos de trabajo existentes en [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] que tengan actividades de  .Net Framework 3.5 producirá un error en `this.SetValue()`. Para abrir proyectos creados con versiones anteriores de .Net Framework, abra primero un flujo de trabajo en blanco en el diseñador y agregue una actividad de  .Net Framework 3.5.  
  
## <a name="to-create-a-net-framework--30-or-35-project-with-visual-studio-2010"></a>Crear un proyecto .NET Framework 3.0 o 3.5 con Visual Studio 2010  
  
1.  Abra [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Seleccione **archivo**, **nueva**, **proyecto**.  
  
3.  En la lista desplegable de la parte superior del cuadro de diálogo, seleccione la versión deseada de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
## <a name="to-upgrade-the-targeted-version-of-the-net-framework"></a>Actualizar la versión de destino de .NET Framework  
  
1.  Haga clic en el proyecto en el Explorador de soluciones y seleccione **propiedades**.  
  
2.  En el **.NET Framework de destino** lista desplegable, seleccione la versión deseada.
