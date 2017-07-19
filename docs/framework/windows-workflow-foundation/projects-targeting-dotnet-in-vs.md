---
title: "Escribir proyectos destinados a .NET Framework 3.0 y 3.5 en Visual Studio 2010 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Escribir proyectos destinados a .NET Framework 3.0 y 3.5 en Visual Studio 2010
Puede utilizar [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] para crear proyectos para [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] versión 3.0 o 3.5.En este tema se describe cómo hacerlo.  
  
> [!NOTE]
>  Al agregar actividades, asegúrese de que se establece la versión deseada de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].Cambiar la versión de destino del flujo de trabajo una vez agregadas las actividades producirá un error de validación en el flujo de trabajo.  
  
> [!WARNING]
>  Abrir flujos de trabajo existentes en [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] que tengan actividades de  .Net Framework 3.5 producirá un error en `this.SetValue()`.Para abrir proyectos creados con versiones anteriores de .Net Framework, abra primero un flujo de trabajo en blanco en el diseñador y agregue una actividad de  .Net Framework 3.5.  
  
## Crear un proyecto .NET Framework 3.0 o 3.5 con Visual Studio 2010  
  
1.  Abra [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Seleccione **Archivo**, **Nuevo**, **Proyecto**.  
  
3.  En la lista desplegable de la parte superior del cuadro de diálogo, seleccione la versión deseada de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
## Actualizar la versión de destino de .NET Framework  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario en el proyecto y seleccione **Propiedades**.  
  
2.  En la lista desplegable **Marco de trabajo de destino**, seleccione la versión deseada.