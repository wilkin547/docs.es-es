---
title: Utilizar el doble búfer
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 9b09210eba0ac3a141219a7cdbff15f22c6ed003
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="using-double-buffering"></a>Utilizar el doble búfer
Puede usar gráficos de doble búfer para reducir el parpadeo en las aplicaciones que contienen operaciones de dibujo complejas. .NET Framework contiene compatibilidad integrada para almacenamiento en búfer doble o puede administrar y representar manualmente gráficos.  
  
## <a name="in-this-section"></a>En esta sección  
 [Gráficos de doble búfer](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 Introduce el soporte de con .NET Framework concepto y los contornos de almacenamiento en búfer doble.  
  
 [Reducir el parpadeo de los gráficos con un búfer doble en formularios y controles](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 Muestra cómo utilizar el valor predeterminado el doble búfer soporte técnico de .NET Framework.  
  
 [Administrar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 Muestra cómo administrar el almacenamiento en búfer doble en aplicaciones.  
  
 [Representar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 Muestra cómo representar gráficos de doble búfer.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 Método de control que permite el almacenamiento en búfer doble.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 Proporciona métodos para crear búferes de gráficos.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 Proporciona acceso al contexto de gráficos almacenados en búfer para un dominio de aplicación.
