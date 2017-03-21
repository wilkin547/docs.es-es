---
title: "Implementación de aplicaciones que hacen referencia al componente PrintForm (Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 016643329d2ee66ca5a32f155cf91e0ee137f38f
ms.lasthandoff: 03/13/2017

---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a>Implementación de aplicaciones que hacen referencia al componente PrintForm (Visual Basic)
Si desea implementar una aplicación que hace referencia el <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>, componente, el componente debe instalarse en el equipo de destino.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [Centro de descarga](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
## <a name="installing-the-printform-as-a-prerequisite"></a>Instalar el componente PrintForm como requisito previo  
 Para implementar correctamente una aplicación, también debe implementar todos los componentes a los que hace referencia la aplicación. El proceso de instalación de componentes de requisito previo se conoce como *arranque*.  
  
 Cuando el <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente está instalado en el equipo de desarrollo, se agrega un paquete de programa previo de Microsoft Visual Basic Power Packs para el [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] directorio de arranque.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Este paquete está disponible al seguir los procedimientos para agregar los requisitos previos para cualquiera [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] o implementación de Windows Installer.  
  
 De forma predeterminada, los componentes de arranque se implementan desde la misma ubicación que el paquete de instalación. Como alternativa, puede implementar los componentes desde una dirección URL o una ubicación de recurso compartido de archivo desde la que los usuarios pueden descargarlos según sea necesario.  
  
> [!NOTE]
>  Para instalar los componentes de arranque, el usuario podría necesitar permisos de usuario administrativo o similares en el equipo. Para [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] aplicaciones, esto significa que el usuario necesitará permisos administrativos para instalar la aplicación, independientemente del nivel de seguridad especificado por la aplicación. Una vez instalada la aplicación, el usuario puede ejecutarla sin permisos administrativos.  
  
 Durante la instalación, los usuarios le pedirá que instale el <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente si no está presente en el equipo de destino.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 Como alternativa al arranque, puede implementar previamente el <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente mediante un sistema de distribución electrónica de software como Microsoft Systems Management Server.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
## <a name="see-also"></a>Vea también  
 [Cómo: instalar requisitos previos mediante una aplicación ClickOnce](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5)   
 [PrintForm (componente)](../../../visual-basic/developing-apps/printing/printform-component.md)
