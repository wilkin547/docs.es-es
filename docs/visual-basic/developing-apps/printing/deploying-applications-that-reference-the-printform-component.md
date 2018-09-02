---
title: Implementación de aplicaciones que hacen referencia al componente PrintForm (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
ms.openlocfilehash: 6384ad6e3bf0520362267eddc8f7bbb05b37f283
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43400431"
---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a>Implementación de aplicaciones que hacen referencia al componente PrintForm (Visual Basic)
Si quiere implementar una aplicación que haga referencia al componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> , el componente debe estar instalado en el equipo de destino.  
  
 Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [centro de descarga de](https://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
## <a name="installing-the-printform-as-a-prerequisite"></a>Instalación de PrintForm como un requisito previo  
 Para implementar correctamente una aplicación, también debe implementar todos los componentes a los que hace referencia la aplicación. El proceso de instalación de componentes de requisito previo se conoce como *arranque*.  
  
 Cuando el <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> componente está instalado en el equipo de desarrollo, se agrega un paquete de programa previo de Microsoft Visual Basic Power Packs en el directorio de programa previo de Visual Studio. Este paquete está disponible al seguir los procedimientos para agregar requisitos previos para cualquier implementación de [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] o Windows Installer.  
  
 De forma predeterminada, los componentes de arranque se implementan desde la misma ubicación que el paquete de instalación. Como alternativa, puede implementar los componentes desde una dirección URL o una ubicación de recurso compartido de archivo desde la que los usuarios pueden descargarlos según sea necesario.  
  
> [!NOTE]
>  Para instalar los componentes de arranque, el usuario podría necesitar permisos de usuario administrativo o similares en el equipo. Para las aplicaciones [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] , esto significa que el usuario necesitará permisos administrativos para instalar la aplicación, independientemente del nivel de seguridad especificado por la aplicación. Una vez instalada la aplicación, el usuario puede ejecutarla sin permisos administrativos.  
  
 Durante la instalación, se pedirá a los usuarios que instalen el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> si no está presente en el equipo de destino.  
  
 Como alternativa al arranque, puede realizar una implementación previa del componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> mediante un sistema electrónico de distribución de software, como Microsoft Systems Management Server.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: Instalar requisitos previos mediante una aplicación ClickOnce](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [PrintForm (componente)](../../../visual-basic/developing-apps/printing/printform-component.md)
