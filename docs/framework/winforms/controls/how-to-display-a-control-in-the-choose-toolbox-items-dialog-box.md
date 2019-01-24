---
title: Procedimiento Mostrar un Control en la elija el cuadro de diálogo de elementos de cuadro de herramientas
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: 56dad16b7a0bd8f0e7423b4a70e7173578150cbe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520456"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Procedimiento Mostrar un Control en la elija el cuadro de diálogo de elementos de cuadro de herramientas
Desarrollar y distribuir controles, es posible que desee esos controles aparezca en el **elegir elementos del cuadro de herramientas** cuadro de diálogo que aparece cuando hace clic en el **cuadro de herramientas** y seleccione  **Elegir elementos**. Puede habilitar el control aparezca en este cuadro de diálogo mediante el procedimiento de registro AssemblyFoldersEx.  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a>Para mostrar el control en el cuadro de diálogo Elegir elementos del cuadro de herramientas  
  
-   Instale al ensamblado del control a la caché global de ensamblados. Para obtener más información, vea [Cómo: Instalar a un ensamblado en la caché Global de ensamblados](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
  
     O bien  
  
-   Registre el control y los ensamblados en tiempo de diseño asociados mediante el procedimiento de registro AssemblyFoldersEx. AssemblyFoldersEx es una ubicación del registro donde otros proveedores almacenan las rutas de acceso para cada versión de framework que admiten. Resolución de tiempo de diseño puede buscar en esta ubicación del registro para buscar los ensamblados de referencia. El script de registro puede especificar los controles que desee que aparezca en el cuadro de herramientas. Para obtener más información, consulte [implementar un Control personalizado y ensamblados en tiempo de diseño (Visual Studio 2013)](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).  
  
## <a name="see-also"></a>Vea también
- [Elegir elementos del cuadro de herramientas (Cuadro de diálogo): Visual Studio](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)
- [Implementación de un Control personalizado y ensamblados en tiempo de diseño (Visual Studio 2013)](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)
- [Desarrollar controles de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
- [Cómo: Instalar a un ensamblado en la caché Global de ensamblados](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)
- [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
