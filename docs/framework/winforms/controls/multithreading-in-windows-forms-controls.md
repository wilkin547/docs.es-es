---
title: Subprocesamiento múltiple en los controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 68822c62a1a195ce3128d51c765cfeba2056955d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536362"
---
# <a name="multithreading-in-windows-forms-controls"></a>Subprocesamiento múltiple en los controles de formularios Windows Forms
En muchas aplicaciones, puede hacer que la interfaz de usuario (UI) sean más receptivos mediante la realización de operaciones que consumen muchos recursos en otro subproceso. Existen una serie de herramientas para multithreading los controles de formularios Windows Forms, incluido el <xref:System.Threading> espacio de nombres, el <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> método y el `BackgroundWorker` componente.  
  
> [!NOTE]
>  El `BackgroundWorker` componente reemplaza y agrega funcionalidad a la <xref:System.Threading> espacio de nombres y el <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> método; sin embargo, estos se conservan para la compatibilidad con versiones anteriores y uso futuro, si elige. Para obtener más información, consulte [general sobre el componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Realizar llamadas seguras para subprocesos en controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Muestra cómo realizar llamadas seguras para subprocesos a controles de formularios Windows Forms.  
  
 [Utilizar un subproceso en segundo plano para buscar archivos](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 Muestra cómo utilizar el <xref:System.Threading> espacio de nombres y el <xref:System.Windows.Forms.Control.BeginInvoke%2A> método para buscar archivos de forma asincrónica.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ComponentModel.BackgroundWorker>  
 Documenta un componente que encapsula un subproceso de trabajo para las operaciones asincrónicas.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Documenta cómo cargar un sonido de forma asincrónica.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Documenta cómo cargar una imagen de forma asincrónica.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 Muestra cómo realizar una operación que consumen muchos recursos con el <xref:System.ComponentModel.BackgroundWorker> componente.  
  
 [Información general sobre el componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 Proporciona temas que describen cómo utilizar el <xref:System.ComponentModel.BackgroundWorker> componente para las operaciones asincrónicas.
