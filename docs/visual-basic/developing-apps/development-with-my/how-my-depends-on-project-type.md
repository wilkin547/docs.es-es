---
title: "C&#243;mo My depende del tipo de proyecto (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "_MYTYPE"
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# C&#243;mo My depende del tipo de proyecto (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My` sólo expone los objetos que requiere un tipo de proyecto determinado.  Por ejemplo, el objeto `My.Forms` está disponible en una aplicación de Windows Forms pero no en una aplicación de consola.  En este tema se describe qué objetos `My` están disponibles en diferentes tipos de proyecto.  
  
## My en aplicaciones Windows y sitios Web  
 `My` sólo expone objetos útiles en el tipo de proyecto actual; suprime los objetos que no son aplicables.  Por ejemplo, la imagen siguiente muestra el modelo de objetos `My` en un proyecto de formularios Windows Forms.  
  
 ![Forma de My en una aplicación de Windows Forms](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 En un proyecto de sitio Web, `My` expone los objetos que son relevantes para un desarrollador Web \(como los objetos `My.Request` y `My.Response`\) y suprime los objetos que no lo son \(como el objeto `My.Forms`\).  La imagen siguiente muestra el modelo de objetos `My` en un proyecto de sitio Web:  
  
 ![Forma de My en una aplicación Web](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## Detalles del proyecto  
 La tabla siguiente muestra los objetos `My` habilitados de forma predeterminada para ocho tipos de proyecto: aplicación Windows, biblioteca de clases, aplicación de consola, biblioteca de controles de Windows, biblioteca de controles Web, servicio de Windows, vacío y sitio Web.  
  
 Existen tres versiones del objeto `My.Application`, dos versiones del objeto `My.Computer` y dos versiones del objeto `My.User`; en las notas al pie incluidas después de la tabla se incluyen detalles sobre estas versiones.  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|Objeto My|Aplicación Windows|Biblioteca de clases|Aplicación de consola|Biblioteca de controles de Windows|Biblioteca de controles Web|Servicio de Windows|Vacío|Sitio Web|  
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
  
 <sup>1</sup> Versión para formularios Windows Forms de `My.Application`.  Se deriva de la versión de consola \(vea la nota 3\); agrega compatibilidad para interactuar con las ventanas de la aplicación y proporciona el modelo de aplicaciones de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 <sup>2</sup> Versión para bibliotecas de `My.Application`.  Proporciona la funcionalidad básica que necesita una aplicación: proporciona miembros para escribir en el registro de aplicaciones y para tener acceso a información de la aplicación.  
  
 <sup>3</sup> Versión para consola de `My.Application`.  Deriva de la versión para bibliotecas \(vea la nota 2\) y agrega miembros adicionales para tener acceso a los argumentos de línea de comandos de la aplicación y a información de la implementación ClickOnce.  
  
 <sup>4</sup> Versión para Windows de `My.Computer`.  Deriva de la versión para servidor \(vea la nota 5\) y proporciona acceso u objetos útiles en un equipo cliente, como el teclado, la pantalla y el mouse.  
  
 <sup>5</sup> Versión para servidor de `My.Computer`.  Proporciona información básica sobre el equipo, como el nombre, el acceso al reloj, etc.  
  
 <sup>6</sup> Versión para Windows de `My.User`.  Este objeto se asocia con la identidad actual del subproceso.  
  
 <sup>7</sup> Versión para Web de `My.User`.  Este objeto se asocia con la identidad de usuario de la solicitud HTTP actual de la aplicación.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Personalizar los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)   
 [My.Forms \(Objeto\)](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [My.Request \(Objeto\)](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [My.Response \(Objeto\)](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [My.WebServices \(Objeto\)](../../../visual-basic/language-reference/objects/my-webservices-object.md)