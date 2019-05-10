---
title: Procedimiento para mostrar un control en el cuadro de diálogo Elegir elementos del cuadro de herramientas
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: 4ed3f6ffdf8a86d050b81311c9211767d8b179b8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623598"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Procedimiento para mostrar un control en el cuadro de diálogo Elegir elementos del cuadro de herramientas
Desarrollar y distribuir controles, es posible que desee esos controles aparezca en el **elegir elementos del cuadro de herramientas** cuadro de diálogo que aparece cuando hace clic en el **cuadro de herramientas** y seleccione  **Elegir elementos**. Puede habilitar el control aparezca en este cuadro de diálogo mediante el procedimiento de registro AssemblyFoldersEx.  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a>Para mostrar el control en el cuadro de diálogo Elegir elementos del cuadro de herramientas  
  
- Instale al ensamblado del control a la caché global de ensamblados. Para obtener más información, vea [Cómo: Instalar un ensamblado en la caché global de ensamblados](../../app-domains/how-to-install-an-assembly-into-the-gac.md)  
  
     -o bien-  
  
- Registre el control y los ensamblados en tiempo de diseño asociados mediante el procedimiento de registro AssemblyFoldersEx. AssemblyFoldersEx es una ubicación del registro donde otros proveedores almacenan las rutas de acceso para cada versión de framework que admiten. Resolución de tiempo de diseño puede buscar en esta ubicación del registro para buscar los ensamblados de referencia. El script de registro puede especificar los controles que desee que aparezca en el cuadro de herramientas. Para obtener más información, consulte [implementar un Control personalizado y ensamblados en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100)).  
  
## <a name="see-also"></a>Vea también

- [Elegir elementos del cuadro de herramientas (Cuadro de diálogo): Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))
- [Implementación de un Control personalizado y ensamblados en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))
- [Desarrollar controles de Windows Forms en tiempo de diseño](developing-windows-forms-controls-at-design-time.md)
- [Cómo: Instalar un ensamblado en la caché global de ensamblados](../../app-domains/how-to-install-an-assembly-into-the-gac.md)
- [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
