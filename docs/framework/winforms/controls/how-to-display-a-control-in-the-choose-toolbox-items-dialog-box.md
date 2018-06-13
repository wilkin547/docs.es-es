---
title: 'Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas'
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: 7e452c3d3be131b891ee26555e3085fc31b04517
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531510"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas
Desarrollar y distribuir controles, puede que desee esos controles aparezcan en el **elegir elementos del cuadro de herramientas** cuadro de diálogo que aparece cuando hace clic en el **cuadro de herramientas** y seleccione  **Elegir elementos**. Puede habilitar el control aparezca en este cuadro de diálogo mediante el procedimiento de registro de AssemblyFoldersEx.  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a>Para mostrar el control en el cuadro de diálogo Elegir elementos del cuadro de herramientas  
  
-   Instale al ensamblado de control en la caché global de ensamblados. Para obtener más información, vea [Cómo: instalar un ensamblado en la caché Global de ensamblados](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
  
     -o bien-  
  
-   Registre el control y los ensamblados en tiempo de diseño asociados mediante el procedimiento de registro de AssemblyFoldersEx. AssemblyFoldersEx es una ubicación del registro donde otros proveedores almacenan las rutas de acceso para cada versión de .NET framework admiten. La resolución en tiempo de diseño puede buscar en esta ubicación del registro para encontrar los ensamblados de referencia. El script de registro puede especificar los controles que desea que aparezcan en el cuadro de herramientas. Para obtener más información, consulte [implementar un Control personalizado y ensamblados en tiempo de diseño (Visual Studio 2013)](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).  
  
## <a name="see-also"></a>Vea también  
 [Elegir elementos del cuadro de herramientas (Cuadro de diálogo): Visual Studio](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [Implementar un Control personalizado y ensamblados en tiempo de diseño (Visual Studio 2013)](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [Desarrollar controles de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [Instalar un ensamblado en la memoria caché global de ensamblados](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
