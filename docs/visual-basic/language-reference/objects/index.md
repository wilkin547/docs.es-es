---
title: "Objetos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "objetos [Visual Basic]"
ms.assetid: 651c73e4-dca8-402b-9c6b-e3902b3a3f4b
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Objetos (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Este tema incluye vínculos a otros temas que documentan los objetos en tiempo de ejecución de Visual Basic y contienen tablas con los procedimientos, propiedades y eventos de sus miembros.  
  
## Objetos en tiempo de ejecución de Visual Basic  
  
|||  
|-|-|  
|<xref:Microsoft.VisualBasic.Collection>|Permite ver de manera sencilla un grupo relacionado de elementos como un solo objeto.|  
|<xref:Microsoft.VisualBasic.Information.Err%2A>|Contiene información sobre los errores en tiempo de ejecución.|  
|El objeto `My.Application` consta de las siguientes clases:<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> proporciona miembros que están disponibles en todos los proyectos.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> proporciona miembros que están disponibles en las aplicaciones de Windows Forms.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> proporciona los miembros que están disponibles en las aplicaciones de consola.|Proporciona datos que solo están asociados a la aplicación o DLL actual.  No se puede modificar ninguna información de nivel de sistema con `My.Application`.<br /><br /> Algunos miembros sólo están disponibles para los formularios Windows Forms o las aplicaciones de consola.|  
|`My.Application.Info` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Info%2A>\)|Proporciona las propiedades para obtener información sobre una aplicación, como el número de versión, la descripción, los ensamblados cargados, etc.|  
|`My.Application.Log` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>\)|Proporciona una propiedad y métodos para escribir información de eventos y de excepciones en los agentes de escucha de registro de la aplicación.|  
|`My.Computer` \(<xref:Microsoft.VisualBasic.Devices.Computer>\)|Proporciona las propiedades para manipular los componentes del equipo como el audio, el reloj, el teclado, el sistema de archivos, etc.|  
|`My.Computer.Audio` \(<xref:Microsoft.VisualBasic.Devices.Audio>\)|Proporciona los métodos para reproducir sonidos.|  
|`My.Computer.Clipboard` \(<xref:Microsoft.VisualBasic.Devices.Computer.Clipboard%2A>\)|Proporciona los métodos para manipular el Portapapeles.|  
|`My.Computer.Clock` \(<xref:Microsoft.VisualBasic.Devices.Clock>\)|Proporciona las propiedades para obtener acceso a la hora local actual y a la hora universal coordinada \(equivalente a la hora media de Greenwich\) del reloj del sistema.|  
|`My.Computer.FileSystem` \(<xref:Microsoft.VisualBasic.FileIO.FileSystem>\)|Proporciona las propiedades y los métodos para trabajar con unidades, archivos y directorios.|  
|`My.Computer.FileSystem.SpecialDirectories` \(<xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>\)|Proporciona las propiedades para obtener acceso a los directorios a los que se hace referencia de manera habitual.|  
|`My.Computer.Info` \(<xref:Microsoft.VisualBasic.Devices.ComputerInfo>\)|Proporciona las propiedades para obtener información sobre la memoria del equipo, los ensamblados cargados, el nombre y el sistema operativo.|  
|`My.Computer.Keyboard` \(<xref:Microsoft.VisualBasic.Devices.Keyboard>\)|Proporciona las propiedades para obtener acceso al estado actual del teclado, como las teclas actualmente presionadas, y proporciona un método para enviar la información de que se han presionado teclas a la ventana activa.|  
|`My.Computer.Mouse` \(<xref:Microsoft.VisualBasic.Devices.Mouse>\)|Proporciona las propiedades para obtener información sobre el formato y la configuración del mouse instalado en el equipo local.|  
|`My.Computer.Network` \(<xref:Microsoft.VisualBasic.Devices.Network>\)|Proporciona una propiedad, un evento y métodos para interactuar con la red a la que está conectado el equipo.|  
|`My.Computer.Ports` \(<xref:Microsoft.VisualBasic.Devices.Ports>\)|Proporciona una propiedad y un método para obtener acceso a los puertos serie del equipo.|  
|`My.Computer.Registry` \(<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>\)|Proporciona las propiedades y los métodos para manipular el Registro.|  
|[My.Forms \(Objeto\)](../../../visual-basic/language-reference/objects/my-forms-object.md)|Proporciona las propiedades para obtener acceso a una instancia de cada Windows Form declarado en el proyecto actual.|  
|`My.Log` \(<xref:Microsoft.VisualBasic.Logging.AspLog>\)|Proporciona una propiedad y métodos para escribir la información de los eventos y excepciones en los agentes de escucha de registro de las aplicaciones web.|  
|[My.Request \(Objeto\)](../../../visual-basic/language-reference/objects/my-request-object.md)|Obtiene el objeto <xref:System.Web.HttpRequest> para la página solicitada.  El objeto `My.Request` contiene información sobre la solicitud HTTP actual.<br /><br /> El objeto `My.Request` solo está disponible para las aplicaciones [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].|  
|[My.Resources \(Objeto\)](../../../visual-basic/language-reference/objects/my-resources-object.md)|Proporciona las propiedades y clases para obtener acceso a los recursos de una aplicación.|  
|[My.Response \(Objeto\)](../../../visual-basic/language-reference/objects/my-response-object.md)|Obtiene el objeto <xref:System.Web.HttpResponse> asociado al objeto <xref:System.Web.UI.Page>.  Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.<br /><br /> El objeto `My.Response` solo está disponible para las aplicaciones [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].|  
|[My.Settings \(Objeto\)](../../../visual-basic/language-reference/objects/my-settings-object.md)|Proporciona las propiedades y los métodos para obtener acceso a la configuración de una aplicación.|  
|`My.User` \(<xref:Microsoft.VisualBasic.ApplicationServices.User>\)|Proporciona acceso a la información sobre el usuario actual.|  
|[My.WebServices \(Objeto\)](../../../visual-basic/language-reference/objects/my-webservices-object.md)|Proporciona las propiedades para crear y obtener acceso a una sola instancia de cada servicio Web al que hace referencia el proyecto actual.|  
|<xref:Microsoft.VisualBasic.FileIO.TextFieldParser>|Proporciona los métodos y propiedades para analizar archivos de texto estructurados.|  
  
## Vea también  
 [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)   
 [Visual Basic](../../../visual-basic/index.md)