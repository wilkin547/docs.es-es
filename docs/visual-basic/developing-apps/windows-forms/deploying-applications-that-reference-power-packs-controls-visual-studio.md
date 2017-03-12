---
title: "Implementar aplicaciones que hacen referencia a los controles Power Packs (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Power Packs, implementar"
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Implementar aplicaciones que hacen referencia a los controles Power Packs (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Si desea implementar una aplicación que hace referencia a los controles de Power Packs \(<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\), los controles se deben instalar en el equipo de destino.  
  
## Instalar los controles de Power Packs como requisito previo  
 Para implementar correctamente una aplicación, también debe implementar todos los componentes a los que hace referencia la aplicación.  El proceso de instalación de los componentes necesarios también se denomina *arranque*.  
  
 Al instalar [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] en el equipo de desarrollo, se agrega un arranque de Power Packs al directorio de arranque de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)].  Este paquete está disponible cuando se siguen los procedimientos para agregar los requisitos previos para la implementación de [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)] o Windows Installer.  
  
 De manera predeterminada, los componentes de arranque se implementan desde la misma ubicación que el paquete de instalación.  Opcionalmente, puede implementar los componentes desde una dirección URL o una ubicación de recurso compartido de archivos en la que los usuarios pueden descargarlos si es necesario.  
  
> [!NOTE]
>  Para instalar los componentes de arranque, el usuario podría necesitar permisos de usuario administrativos o similares en el equipo.  Para las aplicaciones [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)], esto significa que el usuario necesitará permisos administrativos para instalar la aplicación, con independencia del nivel de seguridad especificado por la aplicación.  Una vez instalada la aplicación, el usuario puede ejecutarla sin permisos administrativos.  
  
 Durante la instalación, se solicitará a los usuarios que instalen los controles de Power Packs si no están presentes en el equipo de destino.  
  
 Como alternativa al arranque, puede implementar controles de Power Packs previamente implementados mediante un sistema de distribución electrónica de software, como Microsoft Systems Management Server \(SMS\).  
  
## Vea también  
 [How to: Install Prerequisites in Windows Installer Deployment](http://msdn.microsoft.com/es-es/653fc868-2486-429c-b75e-2f9d0c7f6619)   
 [Cómo: Instalar requisitos previos mediante una aplicación ClickOnce](../Topic/How%20to:%20Install%20Prerequisites%20with%20a%20ClickOnce%20Application.md)   
 [Elegir una estrategia de implementación](http://msdn.microsoft.com/es-es/ecd632d8-063c-4028-b785-81bba045107b)   
 [Controles Visual Basic Power Packs](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)