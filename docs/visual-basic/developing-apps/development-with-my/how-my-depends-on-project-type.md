---
description: 'Más información acerca de: Cómo My depende del tipo de proyecto (Visual Basic)'
title: Cómo My depende del tipo de proyecto
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: 69c1ffdbd241816c9061bf4b4feb6d4359258059
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797983"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Cómo My depende del tipo de proyecto (Visual Basic)

`My` expone solo los objetos que un tipo de proyecto determinado requiere. Por ejemplo, el objeto `My.Forms` estará disponible en una aplicación de Windows Forms, pero no en una aplicación de consola. En este tema se describe qué objetos `My` hay disponibles en diferentes tipos de proyectos.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>My en aplicaciones de Windows y sitios web  

 `My` expone solo los objetos que son útiles en el tipo de proyecto actual y suprime los que no procedan. Por ejemplo, en la siguiente imagen se muestra el modelo de objetos de `My` en un proyecto de Windows Forms.  
  
 ![Diagrama que muestra el modelo de objetos de My en una aplicación de Windows Forms](./media/how-my-depends-on-project-type/my-object-model-windows-forms.png)  
  
 En un proyecto de sitio web, `My` expone los objetos que son relevantes para un desarrollador web (como `My.Request` y `My.Response`) y suprime los que no lo sean (como `My.Forms`). En la siguiente imagen se muestra el modelo de objetos de `My` en un proyecto de sitio web:  
  
 ![Diagrama que muestra el modelo de objetos de My en una aplicación web](./media/how-my-depends-on-project-type/my-object-model-web.png)  
  
## <a name="project-details"></a>Detalles del proyecto  

 En la siguiente tabla se muestra qué objetos de `My` están habilitados de forma predeterminada para ocho tipos de proyecto: aplicación de Windows, biblioteca de clases, aplicación de consola, biblioteca de controles de Windows, biblioteca de controles web, servicio de Windows, vacío y sitio web.  
  
 Hay tres versiones del objeto `My.Application`, dos versiones del objeto `My.Computer` y dos versiones del objeto `My.User`. En las notas al pie de la tabla encontrará detalles sobre estas versiones.  
  
|Objeto de My|Aplicación Windows|Biblioteca de clases|Aplicación de consola|Biblioteca de controles de Windows|Biblioteca de controles web|Servicio de Windows|Empty|Sitio web|  
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
  
 <sup>1</sup> Versión de Windows Forms de `My.Application`. Deriva de la versión de consola (ver nota 3); agrega compatibilidad para interactuar con ventanas de la aplicación y proporciona el modelo de aplicación de Visual Basic.  
  
 <sup>2</sup> Versión de biblioteca de `My.Application`. Ofrece la funcionalidad básica que una aplicación necesita: proporciona miembros para escribir en el registro de la aplicación y acceder a la información de la aplicación.  
  
 <sup>3</sup> Versión de consola de `My.Application`. Deriva de la versión de biblioteca (ver nota 2) y agrega más miembros para acceder a argumentos de la línea de comandos de la aplicación y a información de implementación de ClickOnce.  
  
 <sup>4</sup> Versión de Windows de `My.Computer`. Deriva de la versión de servidor (ver nota 5) y da acceso a objetos útiles en un equipo cliente, como el teclado, la pantalla y el ratón.  
  
 <sup>5</sup> Versión de servidor de `My.Computer`. Proporciona información básica sobre el equipo, como el nombre, acceso al reloj, etc.  
  
 <sup>6</sup> Versión de Windows de `My.User`. Este objeto está asociado a la identidad actual del subproceso.  
  
 <sup>7</sup> Versión web de `My.User`. Este objeto está asociado a la identidad del usuario de la solicitud HTTP actual de la aplicación.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Personalización de los objetos que están disponibles en My](../customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Compilación condicional](../../programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../reference/command-line-compiler/define.md)
- [My.Forms (objeto)](../../language-reference/objects/my-forms-object.md)
- [My.Request (objeto)](../../language-reference/objects/my-request-object.md)
- [My.Response (objeto)](../../language-reference/objects/my-response-object.md)
- [My.WebServices (objeto)](../../language-reference/objects/my-webservices-object.md)
