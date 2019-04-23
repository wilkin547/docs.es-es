---
title: Crear actividades de flujo de trabajo mediante la clase Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 1bec10b6ae9fb43319cfb6acbf59133e1acca09c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770779"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>Crear actividades de flujo de trabajo mediante la clase Activity
La manera más sencilla de crear una actividad utilizando Windows Workflow Foundation (WF) en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] consiste en crear una clase que hereda de <xref:System.Activities.Activity> que cree funciones ensamblando personalizado actividades o desde el [integrados Biblioteca de actividades](net-framework-4-5-built-in-activity-library.md). En este tema se muestra cómo crear una actividad que escribe dos mensajes en la consola.

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>Para crear una actividad personalizada mediante el diseñador de actividad

1. Abra Visual Studio 2012.

2. Seleccione Archivo, Nuevo, Proyecto. Seleccione **Workflow 4.0** en **Visual C#** en el **tipos de proyecto** ventana y seleccione el **v2010** nodo. Seleccione **biblioteca de actividades** en el **plantillas** ventana. Dé al nuevo proyecto el nombre "HelloActivity".

3. Abra la nueva actividad.  Arrastre una actividad <xref:System.Activities.Statements.Sequence> desde el cuadro de herramientas a la superficie del diseñador.

4. Arrastre una actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>. Escriba `"Hello World"` (con comillas) en el **texto** campo.

5. Arrastre una segunda actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>, debajo de la primera. Escriba `"Goodbye"` (con comillas) en el **texto** campo.
