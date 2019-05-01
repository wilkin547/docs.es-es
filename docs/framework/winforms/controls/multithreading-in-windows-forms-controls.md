---
title: Subprocesamiento múltiple en los controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cc7f358a62c8057abb77e1f5a28544bb6c858d98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012729"
---
# <a name="multithreading-in-windows-forms-controls"></a>Subprocesamiento múltiple en los controles de formularios Windows Forms
En muchas aplicaciones, puede hacer que la interfaz de usuario (UI) con más capacidad de respuesta mediante la realización de operaciones que requieren mucho tiempo en otro subproceso. Existen varias herramientas para multithreading los controles de Windows Forms, incluido el <xref:System.Threading> espacio de nombres, el <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> método y el `BackgroundWorker` componente.  
  
> [!NOTE]
>  El `BackgroundWorker` componente reemplaza y agrega funcionalidad a la <xref:System.Threading> espacio de nombres y el <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> método; sin embargo, estos se conservan para compatibilidad con versiones anteriores y uso futuro, si elige. Para obtener más información, consulte [general sobre el componente BackgroundWorker](backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Realizar llamadas seguras para subprocesos a controles de formularios Windows Forms](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Muestra cómo realizar llamadas seguras para subprocesos a controles de formularios Windows Forms.  
  
 [Cómo: Usar un subproceso en segundo plano para buscar archivos](how-to-use-a-background-thread-to-search-for-files.md)  
 Se muestra cómo usar el <xref:System.Threading> espacio de nombres y el <xref:System.Windows.Forms.Control.BeginInvoke%2A> método para buscar archivos de forma asincrónica.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ComponentModel.BackgroundWorker>  
 Documenta un componente que encapsula un subproceso de trabajo para las operaciones asincrónicas.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Describe cómo cargar un sonido de forma asincrónica.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Describe cómo cargar una imagen de forma asincrónica.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Cómo: Ejecutar una operación en segundo plano](how-to-run-an-operation-in-the-background.md)  
 Muestra cómo realizar una operación lenta con el <xref:System.ComponentModel.BackgroundWorker> componente.  
  
 [Información general sobre el componente BackgroundWorker](backgroundworker-component-overview.md)  
 Proporciona temas que describen cómo usar el <xref:System.ComponentModel.BackgroundWorker> componente para las operaciones asincrónicas.
