---
title: "Implementación de aplicaciones que hacen referencia a controles de Power Packs (Visual Studio) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4d342e655dcfe18ed3b5fc1d2710571ed8e3369e
ms.lasthandoff: 03/13/2017

---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a>Implementación de aplicaciones que hacen referencia a controles de Power Packs (Visual Studio)
Si desea implementar una aplicación que hace referencia a los controles Power Packs (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), los controles deben instalarse en el equipo de destino.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> </xref:Microsoft.VisualBasic.PowerPacks.OvalShape> </xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a>Instalar los controles Power Packs como requisito previo  
 Para implementar correctamente una aplicación, también debe implementar todos los componentes a los que hace referencia la aplicación. El proceso de instalación de componentes de requisito previo se conoce como *arranque*.  
  
 Cuando [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] está instalado en el equipo de desarrollo, Power Packs de un paquete de programa previo se agrega a la [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] directorio de arranque. Este paquete está disponible al seguir los procedimientos para agregar los requisitos previos para cualquiera [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] o implementación de Windows Installer.  
  
 De forma predeterminada, los componentes de arranque se implementan desde la misma ubicación que el paquete de instalación. Como alternativa, puede implementar los componentes desde una dirección URL o una ubicación de recurso compartido de archivo desde la que los usuarios pueden descargarlos según sea necesario.  
  
> [!NOTE]
>  Para instalar los componentes de arranque, el usuario podría necesitar permisos de usuario administrativo o similares en el equipo. Para [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] aplicaciones, esto significa que el usuario necesitará permisos administrativos para instalar la aplicación, independientemente del nivel de seguridad especificado por la aplicación. Una vez instalada la aplicación, el usuario puede ejecutarla sin permisos administrativos.  
  
 Durante la instalación, los usuarios le pedirá que instale los controles Power Packs si no están presentes en el equipo de destino.  
  
 Como alternativa al arranque, puede implementar los controles Power Packs previamente mediante un sistema de distribución electrónica de software como Microsoft Systems Management Server.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: instalar requisitos previos mediante una aplicación ClickOnce](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5)   
 [Controles Visual Basic Power Packs](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
