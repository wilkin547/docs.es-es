---
title: Utilizar el doble búfer
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 5b22336221c7bdda3c9dd7adf23308a2b0bad450
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169920"
---
# <a name="using-double-buffering"></a>Utilizar el doble búfer
Puede usar gráficos de doble búfer para reducir el parpadeo en las aplicaciones que contienen operaciones de pintura complejas. .NET Framework contiene compatibilidad integrada para el búfer doble o puede administrar y representar manualmente gráficos.  
  
## <a name="in-this-section"></a>En esta sección  
 [Gráficos de doble búfer](double-buffered-graphics.md)  
 Presenta compatibilidad de con .NET Framework concepto y esquemas de almacenamiento en búfer doble.  
  
 [Cómo: Reducir el parpadeo de gráficos con un búfer doble en formularios y controles](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 Muestra cómo usar el valor predeterminado en doble búfer de soporte técnico de .NET Framework.  
  
 [Cómo: Administrar manualmente gráficos almacenados en búfer](how-to-manually-manage-buffered-graphics.md)  
 Muestra cómo administrar el almacenamiento en búfer doble en aplicaciones.  
  
 [Cómo: Representar manualmente gráficos almacenados en búfer](how-to-manually-render-buffered-graphics.md)  
 Muestra cómo representar gráficos de doble búfer.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.Control.SetStyle%2A> Método de control que permite el almacenamiento en doble búfer.  
  
 <xref:System.Drawing.BufferedGraphicsContext> Proporciona métodos para crear búferes de gráficos.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 Proporciona acceso al contexto de gráficos almacenados en búfer para un dominio de aplicación.
