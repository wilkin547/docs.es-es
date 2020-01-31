---
title: Multithreading en controles
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742146"
---
# <a name="multithreading-in-windows-forms-controls"></a>Multithreading en los controles de Windows Forms
En muchas aplicaciones, puede hacer que la interfaz de usuario (UI) tenga mayor capacidad de respuesta al realizar operaciones que consumen mucho tiempo en otro subproceso. Hay varias herramientas disponibles para el multithreading de los controles Windows Forms, incluido el espacio de nombres <xref:System.Threading>, el método <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> y el componente `BackgroundWorker`.  
  
> [!NOTE]
> El componente `BackgroundWorker` reemplaza y agrega funcionalidad al espacio de nombres <xref:System.Threading> y al método <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>; sin embargo, se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide. Para obtener más información, vea [información general sobre el componente BackgroundWorker](backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>Esta sección  
 [Realizar llamadas seguras para subprocesos en controles de formularios Windows Forms](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Muestra cómo realizar llamadas seguras para subprocesos a controles Windows Forms.  
  
 [Utilizar un subproceso en segundo plano para buscar archivos](how-to-use-a-background-thread-to-search-for-files.md)  
 Muestra cómo usar el espacio de nombres <xref:System.Threading> y el método <xref:System.Windows.Forms.Control.BeginInvoke%2A> para buscar archivos de forma asincrónica.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ComponentModel.BackgroundWorker>  
 Documenta un componente que encapsula un subproceso de trabajo para las operaciones asincrónicas.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Documenta cómo cargar un sonido de forma asincrónica.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Documenta cómo cargar una imagen de forma asincrónica.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Ejecutar una operación en segundo plano](how-to-run-an-operation-in-the-background.md)  
 Muestra cómo realizar una operación que consume mucho tiempo con el componente de <xref:System.ComponentModel.BackgroundWorker>.  
  
 [Información general sobre el componente BackgroundWorker](backgroundworker-component-overview.md)  
 Proporciona temas que describen cómo utilizar el componente de <xref:System.ComponentModel.BackgroundWorker> para las operaciones asincrónicas.
