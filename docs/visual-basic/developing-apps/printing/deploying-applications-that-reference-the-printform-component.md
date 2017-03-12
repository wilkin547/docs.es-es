---
title: "Deploying Applications That Reference the PrintForm Component (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "PrintForm component [Visual Basic], deploying"
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Deploying Applications That Reference the PrintForm Component (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Si quiere implementar una aplicación que haga referencia al componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>, el componente debe estar instalado en el equipo de destino.  
  
 Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [Centro de descarga](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
## Instalación de PrintForm como un requisito previo  
 Para implementar correctamente una aplicación, también debe implementar todos los componentes a los que hace referencia la aplicación. El proceso de instalación de componentes de requisito previo se conoce como *arranque*.  
  
 Si el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> está instalado en el equipo de desarrollo, se agrega un paquete de arranque de Microsoft Visual Basic PowerPacks al directorio de arranque de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]. Este paquete está disponible al seguir los procedimientos para agregar requisitos previos para cualquier implementación de [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)] o Windows Installer.  
  
 De forma predeterminada, los componentes de arranque se implementan desde la misma ubicación que el paquete de instalación. Como alternativa, puede implementar los componentes desde una dirección URL o una ubicación de recurso compartido de archivo desde la que los usuarios pueden descargarlos según sea necesario.  
  
> [!NOTE]
>  Para instalar los componentes de arranque, el usuario podría necesitar permisos de usuario administrativo o similares en el equipo. Para las aplicaciones [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)], esto significa que el usuario necesitará permisos administrativos para instalar la aplicación, independientemente del nivel de seguridad especificado por la aplicación. Una vez instalada la aplicación, el usuario puede ejecutarla sin permisos administrativos.  
  
 Durante la instalación, se pedirá a los usuarios que instalen el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> si no está presente en el equipo de destino.  
  
 Como alternativa al arranque, puede realizar una implementación previa del componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> mediante un sistema electrónico de distribución de software, como Microsoft Systems Management Server.  
  
## Vea también  
 [Cómo: Instalar requisitos previos mediante una aplicación ClickOnce](../Topic/How%20to:%20Install%20Prerequisites%20with%20a%20ClickOnce%20Application.md)   
 [No está en la compilación: Elegir una estrategia de implementación](http://msdn.microsoft.com/es-es/ecd632d8-063c-4028-b785-81bba045107b)   
 [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)