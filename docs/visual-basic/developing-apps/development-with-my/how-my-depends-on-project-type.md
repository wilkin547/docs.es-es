---
title: Cómo My depende del tipo de proyecto (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d931a2034d681c4e14cc35ecfbd9ad7accf5afaa
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Cómo My depende del tipo de proyecto (Visual Basic)
`My` muestra sólo los objetos requeridos por un tipo de proyecto determinado. Por ejemplo, el `My.Forms` objeto está disponible en una aplicación de Windows Forms pero no está disponible en una aplicación de consola. En este tema se describe qué `My` objetos están disponibles en diferentes tipos de proyectos.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>Mi Windows en las aplicaciones y sitios Web  
 `My` expone sólo los objetos que son útiles en el tipo de proyecto actual; Suprime los objetos que no son aplicables. Por ejemplo, la siguiente imagen muestra la `My` modelo de objetos en un proyecto de formularios Windows Forms.  
  
 ![Forma de My en una aplicación de formularios Windows Forms](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 En un proyecto de sitio Web, `My` expone objetos que son relevantes para un desarrollador Web (como el `My.Request` y `My.Response` objetos) y suprime los objetos que no son relevantes (como la `My.Forms` objeto). La siguiente imagen muestra la `My` modelo de objetos en un proyecto de sitio Web:  
  
 ![Forma de My en una aplicación Web](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## <a name="project-details"></a>Detalles del proyecto  
 En la tabla siguiente se muestra qué `My` objetos están habilitados de forma predeterminada para ocho tipos de proyecto: Windows aplicación, clase, biblioteca, aplicación de consola, Windows biblioteca de controles, Web biblioteca de control, Windows service, vacío y sitio Web.  
  
 Hay tres versiones de la `My.Application` (objeto), dos versiones de la `My.Computer` objeto y dos versiones de `My.User` objeto; se proporcionan detalles acerca de estas versiones en los pies de página después de la tabla.  
  
|My (objeto)|Aplicación Windows|Biblioteca de clases|Aplicación de consola|Biblioteca de controles de Windows|Biblioteca de controles Web|Servicio de Windows|Empty|Sitio web|  
|---|---|---|---|---|---|---|---|---|  
|`My.Application`|**Sí** <sup>1</sup>|**Sí** <sup>2</sup>|**Sí** <sup>3</sup>|**Sí** <sup>2</sup>|No|**Sí** <sup>3</sup>|No|No|  
|`My.Computer`|**Sí** <sup>4</sup>|**Sí** <sup>4</sup>|**Sí** <sup>4</sup>|**Sí** <sup>4</sup>|**Sí** <sup>5</sup>|**Sí** <sup>4</sup>|No|**Sí** <sup>5</sup>|  
|`My.Forms`|**Sí**|No|No|**Sí**|No|No|No|No|  
|`My.Log`|No|No|No|No|No|No|No|**Sí**|  
|`My.Request`|No|No|No|No|No|No|No|**Sí**|  
|`My.Resources`|**Sí**|**Sí**|**Sí**|**Sí**|**Sí**|**Sí**|No|No|  
|`My.Response`|No|No|No|No|No|No|No|**Sí**|  
|`My.Settings`|**Sí**|**Sí**|**Sí**|**Sí**|**Sí**|**Sí**|No|No|  
|`My.User`|**Sí** <sup>6</sup>|**Sí** <sup>6</sup>|**Sí** <sup>6</sup>|**Sí** <sup>6</sup>|**Sí** <sup>7</sup>|**Sí** <sup>6</sup>|No|**Sí** <sup>7</sup>|  
|`My.WebServices`|**Sí**|**Sí**|**Sí**|**Sí**|**Sí**|**Sí**|No|No|  
  
 <sup>1</sup> versión de Windows Forms de `My.Application`. Se deriva de la versión de la consola (vea la nota 3); Agrega compatibilidad para interactuar con las ventanas de la aplicación y proporciona el modelo de aplicaciones de Visual Basic.  
  
 <sup>2</sup> versión de biblioteca de `My.Application`. Proporciona la funcionalidad básica que necesita una aplicación: proporciona miembros para escribir en el registro de aplicación y acceder a información de la aplicación.  
  
 <sup>3</sup> versión de la consola de `My.Application`. Se deriva de la versión de biblioteca (consulte la nota 2), y agrega miembros adicionales para tener acceso a información sobre la implementación de ClickOnce y los argumentos de línea de comandos de la aplicación.  
  
 <sup>4</sup> versión de Windows de `My.Computer`. Se deriva de la versión del servidor (vea la nota 5) y proporciona acceso a objetos útiles en un equipo cliente, como el teclado, la pantalla y el mouse.  
  
 <sup>5</sup> versión del servidor de `My.Computer`. Proporciona información básica sobre el equipo, como el nombre, el acceso a la hora y así sucesivamente.  
  
 <sup>6</sup> versión de Windows de `My.User`. Este objeto está asociado con la identidad del subproceso actual.  
  
 <sup>7</sup> versión web de `My.User`. Este objeto está asociado con la identidad del usuario de la solicitud HTTP actual de la aplicación.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.Logging.Log>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [Personalización de los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [My.Forms (objeto)](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.Request (objeto)](../../../visual-basic/language-reference/objects/my-request-object.md)  
 [My.Response (objeto)](../../../visual-basic/language-reference/objects/my-response-object.md)  
 [My.WebServices (objeto)](../../../visual-basic/language-reference/objects/my-webservices-object.md)
