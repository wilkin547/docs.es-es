---
title: Crear actividades de flujo de trabajo mediante la clase Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 21f1c8b1249d41029fa7a19360e96ad866c823a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293850"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>Crear actividades de flujo de trabajo mediante la clase Activity

La manera más básica de crear una actividad mediante Windows Workflow Foundation (WF) en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] es crear una clase que herede de <xref:System.Activities.Activity> que crea la funcionalidad ensamblando actividades o actividades personalizadas desde la [biblioteca de actividades integrada](net-framework-4-5-built-in-activity-library.md). En este tema se muestra cómo crear una actividad que escribe dos mensajes en la consola.

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>Para crear una actividad personalizada mediante el diseñador de actividad

1. Abra Visual Studio 2012.

2. Seleccione Archivo, Nuevo, Proyecto. Seleccione **flujo de trabajo 4,0** en **Visual C#** en la ventana **tipos de proyecto** y seleccione el nodo **V2010** . Seleccione **biblioteca de actividades** en la ventana **plantillas** . Dé al nuevo proyecto el nombre "HelloActivity".

3. Abra la nueva actividad.  Arrastre una actividad <xref:System.Activities.Statements.Sequence> desde el cuadro de herramientas a la superficie del diseñador.

4. Arrastre una actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>. Escriba `"Hello World"` (con comillas) en el campo de **texto** .

5. Arrastre una segunda actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>, debajo de la primera. Escriba `"Goodbye"` (con comillas) en el campo de **texto** .
