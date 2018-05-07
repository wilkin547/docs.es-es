---
title: Implementación de aplicaciones que hacen referencia a controles Power Packs (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
ms.openlocfilehash: bd235bc0b4a7f9978333931ae1dce012c0950374
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a>Implementación de aplicaciones que hacen referencia a controles Power Packs (Visual Studio)
Si va a implementar una aplicación que hace referencia a los controles Power Packs (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), los controles deben instalarse en el equipo de destino.  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a>Instalación de los controles Power Packs como requisito previo  
 Para implementar correctamente una aplicación, también debe implementar todos los componentes a los que hace referencia la aplicación. El proceso de instalación de componentes de requisito previo se conoce como *arranque*.  
  
 Cuando Visual Studio está instalado en el equipo de desarrollo, se agrega un paquete de programa previo de los Power Packs en el directorio de programa previo de Visual Studio. Este paquete está disponible al seguir los procedimientos para agregar requisitos previos para cualquier implementación de [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] o Windows Installer.  
  
 De forma predeterminada, los componentes de arranque se implementan desde la misma ubicación que el paquete de instalación. Como alternativa, puede implementar los componentes desde una dirección URL o una ubicación de recurso compartido de archivo desde la que los usuarios pueden descargarlos según sea necesario.  
  
> [!NOTE]
>  Para instalar los componentes de arranque, el usuario podría necesitar permisos de usuario administrativo o similares en el equipo. Para las aplicaciones [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] , esto significa que el usuario necesitará permisos administrativos para instalar la aplicación, independientemente del nivel de seguridad especificado por la aplicación. Una vez instalada la aplicación, el usuario puede ejecutarla sin permisos administrativos.  
  
 Durante la instalación, los usuarios se le pedirá que instale los controles Power Packs si no están presentes en el equipo de destino.  
  
 Como alternativa al arranque, puede implementar previamente los controles Power Packs mediante un sistema de distribución electrónica de software como Microsoft Systems Management Server.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: Instalar requisitos previos mediante una aplicación ClickOnce](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [Controles de Power Packs de Visual Basic](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
