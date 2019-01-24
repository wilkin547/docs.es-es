---
title: Implementación de aplicaciones que hacen referencia a controles Power Packs (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
ms.openlocfilehash: 3fd46a6e8aad61d2f8ce5a230c856470f913d0bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551779"
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a>Implementación de aplicaciones que hacen referencia a controles Power Packs (Visual Studio)
Si desea implementar una aplicación que hace referencia a los controles Power Packs (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), los controles deben instalarse en el equipo de destino.  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a>Instalación de los controles Power Packs como requisito previo  
 Para implementar correctamente una aplicación, también debe implementar todos los componentes a los que hace referencia la aplicación. El proceso de instalación de componentes de requisito previo se conoce como *arranque*.  
  
 Cuando se instala Visual Studio en el equipo de desarrollo, se agrega un paquete de programa previo de los Power Packs en el directorio de programa previo de Visual Studio. Este paquete está disponible al seguir los procedimientos para agregar requisitos previos para cualquier implementación de [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] o Windows Installer.  
  
 De forma predeterminada, los componentes de arranque se implementan desde la misma ubicación que el paquete de instalación. Como alternativa, puede implementar los componentes desde una dirección URL o una ubicación de recurso compartido de archivo desde la que los usuarios pueden descargarlos según sea necesario.  
  
> [!NOTE]
>  Para instalar los componentes de arranque, el usuario podría necesitar permisos de usuario administrativo o similares en el equipo. Para las aplicaciones [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] , esto significa que el usuario necesitará permisos administrativos para instalar la aplicación, independientemente del nivel de seguridad especificado por la aplicación. Una vez instalada la aplicación, el usuario puede ejecutarla sin permisos administrativos.  
  
 Durante la instalación, se pedirá a los usuarios para instalar los controles Power Packs si no están presentes en el equipo de destino.  
  
 Como alternativa al arranque, puede implementar los controles Power Packs previamente mediante un sistema de distribución electrónica de software como Microsoft Systems Management Server.  
  
## <a name="see-also"></a>Vea también
- [Cómo: Instalación de requisitos previos con una aplicación ClickOnce](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)
- [Controles de Visual Basic Power Packs](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
