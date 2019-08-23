---
title: Subprocesamiento múltiple en los controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cf6790172b7445ad154eead5d17f8efddd78ffee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952678"
---
# <a name="multithreading-in-windows-forms-controls"></a>Subprocesamiento múltiple en los controles de formularios Windows Forms
En muchas aplicaciones, puede hacer que la interfaz de usuario (UI) tenga mayor capacidad de respuesta al realizar operaciones que consumen mucho tiempo en otro subproceso. Hay varias herramientas disponibles para el multithreading de los controles Windows Forms, incluido el <xref:System.Threading> espacio de nombres <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> , el método y `BackgroundWorker` el componente.  
  
> [!NOTE]
> El `BackgroundWorker` componente reemplaza y agrega funcionalidad <xref:System.Threading> al espacio de nombres y <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> al método; sin embargo, se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide. Para obtener más información, vea [información general sobre el componente BackgroundWorker](backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Realizar llamadas seguras para subprocesos a controles de Windows Forms](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Muestra cómo realizar llamadas seguras para subprocesos a controles Windows Forms.  
  
 [Cómo: Usar un subproceso en segundo plano para buscar archivos](how-to-use-a-background-thread-to-search-for-files.md)  
 Muestra cómo usar el <xref:System.Threading> espacio de nombres y el <xref:System.Windows.Forms.Control.BeginInvoke%2A> método para buscar archivos de forma asincrónica.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ComponentModel.BackgroundWorker>  
 Documenta un componente que encapsula un subproceso de trabajo para las operaciones asincrónicas.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Documenta cómo cargar un sonido de forma asincrónica.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Documenta cómo cargar una imagen de forma asincrónica.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Cómo: Ejecutar una operación en segundo plano](how-to-run-an-operation-in-the-background.md)  
 Muestra cómo realizar una operación que consume mucho tiempo con el <xref:System.ComponentModel.BackgroundWorker> componente.  
  
 [Información general sobre el componente BackgroundWorker](backgroundworker-component-overview.md)  
 Proporciona temas que describen cómo usar el <xref:System.ComponentModel.BackgroundWorker> componente para las operaciones asincrónicas.
