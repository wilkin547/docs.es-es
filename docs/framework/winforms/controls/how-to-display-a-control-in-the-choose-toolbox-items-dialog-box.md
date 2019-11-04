---
title: 'Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas'
ms.date: 08/23/2019
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: db4b3ac020e967a6a0c291103d825ac71cebda23
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458271"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas

A medida que desarrolle y distribuya controles, puede que desee que estos controles aparezcan en el cuadro de diálogo **elegir elementos del cuadro de herramientas** de Visual Studio, que se muestra al hacer clic con el botón secundario en el cuadro de **herramientas** y seleccionar **elegir elementos**. Puede habilitar el control para que aparezca en este cuadro de diálogo mediante el procedimiento de registro de AssemblyFoldersEx.

Para mostrar el control en el cuadro de diálogo Elegir elementos del cuadro de herramientas:

- Instale el ensamblado de control en la caché global de ensamblados. Para obtener más información, vea [Cómo: Instalar un ensamblado en la memoria caché global de ensamblados](../../app-domains/install-assembly-into-gac.md).

  o bien

- Registre el control y sus ensamblados en tiempo de diseño asociados mediante el procedimiento de registro de AssemblyFoldersEx. AssemblyFoldersEx es una ubicación del registro donde los proveedores de terceros almacenan rutas de acceso para cada versión del marco que admiten. La resolución en tiempo de diseño puede buscar en esta ubicación del registro para buscar ensamblados de referencia. El script del registro puede especificar los controles que desea que aparezcan en el cuadro de herramientas.

## <a name="see-also"></a>Vea también

- [Desarrollar controles de Windows Forms en tiempo de diseño](developing-windows-forms-controls-at-design-time.md)
- [Instalar un ensamblado en la memoria caché global de ensamblados](../../app-domains/install-assembly-into-gac.md)
- [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
