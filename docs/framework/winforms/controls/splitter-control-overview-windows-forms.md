---
title: Información general sobre Splitter (Control, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 0477f68aaf67d4b29c491052999ff7784e736669
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176415"
---
# <a name="splitter-control-overview-windows-forms"></a>Información general sobre Splitter (Control, formularios Windows Forms)
> [!IMPORTANT]
>  Aunque el control <xref:System.Windows.Forms.SplitContainer> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.Splitter> de las versiones anteriores, <xref:System.Windows.Forms.Splitter> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, si se desea.  
  
 Windows Forms <xref:System.Windows.Forms.Splitter> controles se usan para cambiar el tamaño de los controles acoplados en tiempo de ejecución. El <xref:System.Windows.Forms.Splitter> control suele utilizarse en formularios con controles que tienen distintas longitudes de datos que se va a presentar, como el Explorador de Windows, cuyos paneles de datos contienen información de diversos anchos en momentos diferentes.  
  
## <a name="working-with-the-splitter-control"></a>Trabajar con el Control divisor  
 Cuando el usuario sitúa el puntero del mouse sobre el borde de un control que se puede cambiar el tamaño de un control divisor desacoplado, el puntero cambia de apariencia para indicar que se puede cambiar el tamaño del control. Con el control divisor, el usuario puede cambiar el tamaño del control acoplado inmediatamente anterior. Por lo tanto, para permitir al usuario cambiar el tamaño de un control acoplado en tiempo de ejecución, acople el control para cambiar de tamaño a un borde de un contenedor y, a continuación, acoplar un control divisor en el mismo lado de ese contenedor.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.SplitContainer>
- [Filtrar para acoplar controles en formularios Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
