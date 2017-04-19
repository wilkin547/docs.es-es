---
title: "Cómo My depende de tipo de proyecto (Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: d193dade94980f04b31605ea6fa968f9fa7d0ad6
ms.lasthandoff: 03/13/2017

---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Cómo My depende del tipo de proyecto (Visual Basic)
`My`muestra sólo los objetos requeridos por un tipo de proyecto determinado. Por ejemplo, el `My.Forms` objeto está disponible en una aplicación de Windows Forms pero no está disponible en una aplicación de consola. En este tema se describe los `My` objetos están disponibles en diferentes tipos de proyectos.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>Windows en aplicaciones y sitios Web  
 `My`muestra sólo los objetos que son útiles en el tipo de proyecto actual; Suprime los objetos que no son aplicables. Por ejemplo, la siguiente imagen muestra la `My` modelo de objetos en un proyecto de formularios Windows Forms.  
  
 ![Forma de My en una aplicación de formularios Windows Forms](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 En un proyecto de sitio Web, `My` expone objetos que son relevantes para un desarrollador Web (como el `My.Request` y `My.Response` objetos) y suprime los objetos que no son relevantes (como la `My.Forms` objeto). La siguiente imagen muestra la `My` modelo de objetos en un proyecto de sitio Web:  
  
 ![Forma de My en una aplicación Web](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## <a name="project-details"></a>Detalles del proyecto  
 La siguiente tabla muestra qué `My` los objetos están habilitados de forma predeterminada para ocho tipos de proyecto: Windows application, clase, biblioteca, aplicación de consola, Windows biblioteca de controles, Web biblioteca de control, Windows service, vacío y sitio Web.  
  
 Hay tres versiones de la `My.Application` (objeto), dos versiones de la `My.Computer` objeto y dos versiones de `My.User` objeto; se proporcionan detalles acerca de estas versiones en los pies de página después de la tabla.  
  
|My (objeto)|Aplicación Windows|Biblioteca de clases|Aplicación de consola|Biblioteca de controles de Windows|Biblioteca de controles web|Servicio de Windows|Empty|Sitio web|  
|---|---|---|---|---|---|---|---|---|  
|`My.Application`|**Yes** <sup>1</sup>|**Yes** <sup>2</sup>|**Yes** <sup>3</sup>|**Yes** <sup>2</sup>|No|**Yes** <sup>3</sup>|No|No|  
|`My.Computer`|**Yes** <sup>4</sup>|**Yes** <sup>4</sup>|**Yes** <sup>4</sup>|**Yes** <sup>4</sup>|**Yes** <sup>5</sup>|**Yes** <sup>4</sup>|No|**Yes** <sup>5</sup>|  
|`My.Forms`|**Sí**|No|No|**Sí**|No|No|No|No|  
|`My.Log`|No|No|No|No|No|No|No|**Sí**|  
|`My.Request`|No|No|No|No|No|No|No|**Sí**|  
|`My.Resources`|**Sí**|**Sí**|**Sí**|**Sí**|**Sí**|**Sí**|No|No|  
|`My.Response`|No|No|No|No|No|No|No|**Sí**|  
|`My.Settings`|**Sí**|**Sí**|**Sí**|**Sí**|**Sí**|**Sí**|No|No|  
|`My.User`|**Yes** <sup>6</sup>|**Yes** <sup>6</sup>|**Yes** <sup>6</sup>|**Yes** <sup>6</sup>|**Yes** <sup>7</sup>|**Yes** <sup>6</sup>|No|**Yes** <sup>7</sup>|  
|`My.WebServices`|**Sí**|**Sí**|**Sí**|**Sí**|**Sí**|**Sí**|No|No|  
  
 <sup>1</sup> versión de Windows Forms `My.Application`. Se deriva de la versión de consola (Véase la nota 3); Agrega compatibilidad para interactuar con las ventanas de la aplicación y proporciona el [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] modelo de aplicación.  
  
 <sup>2</sup> versión de biblioteca de `My.Application`. Proporciona la funcionalidad básica que necesita una aplicación: proporciona miembros para escribir en el registro de aplicación y el acceso a información de la aplicación.  
  
 <sup>3</sup> versión de la consola de `My.Application`. Se deriva de la versión de biblioteca (consulte la nota 2), y agrega miembros adicionales para tener acceso a información sobre la implementación de ClickOnce y los argumentos de línea de comandos de la aplicación.  
  
 <sup>4</sup> versión de Windows de `My.Computer`. Se deriva de la versión del servidor (vea la nota 5) y proporciona acceso a objetos útiles en un equipo cliente, como el teclado, la pantalla y el mouse.  
  
 <sup>5</sup> versión del servidor de `My.Computer`. Proporciona información básica sobre el equipo, como el nombre, el acceso a la hora y así sucesivamente.  
  
 <sup>6</sup> versión de Windows de `My.User`. Este objeto se asocia con la identidad del subproceso actual.  
  
 <sup>7</sup> versión web de `My.User`. Este objeto se asocia con la identidad del usuario de la solicitud HTTP actual de la aplicación.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer></xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log></xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User></xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Personalizar los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)   
 [My.Forms (objeto)](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [My.Request (objeto)](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [My.Response (objeto)](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [My.WebServices (objeto)](../../../visual-basic/language-reference/objects/my-webservices-object.md)
