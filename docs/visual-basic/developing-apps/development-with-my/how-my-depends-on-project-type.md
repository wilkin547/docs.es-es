---
title: Cómo My depende del tipo de proyecto
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: 975b8feb001bcab22185be0a360b0512de099b79
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330265"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Cómo My depende del tipo de proyecto (Visual Basic)

`My` expone solo los objetos que requiere un tipo de proyecto determinado. Por ejemplo, el objeto `My.Forms` está disponible en una aplicación Windows Forms, pero no está disponible en una aplicación de consola. En este tema se describe qué objetos `My` están disponibles en diferentes tipos de proyectos.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>Mis en aplicaciones y sitios web de Windows  

 `My` expone solo los objetos que son útiles en el tipo de proyecto actual; suprime los objetos que no son aplicables. Por ejemplo, la siguiente imagen muestra el modelo de objetos de `My` en un proyecto de Windows Forms.  
  
 ![Diagrama que muestra el modelo My Object en una aplicación Windows Forms.](./media/how-my-depends-on-project-type/my-object-model-windows-forms.png)  
  
 En un proyecto de sitio web, `My` expone objetos que son relevantes para un desarrollador web (como los objetos `My.Request` y `My.Response`) mientras se suprimen objetos que no son relevantes (como el objeto `My.Forms`). En la imagen siguiente se muestra el modelo de objetos de `My` en un proyecto de sitio web:  
  
 ![Diagrama que muestra el modelo My Object en una aplicación Web.](./media/how-my-depends-on-project-type/my-object-model-web.png)  
  
## <a name="project-details"></a>Detalles del proyecto  

 En la tabla siguiente se muestra qué objetos `My` están habilitados de forma predeterminada para ocho tipos de proyecto: aplicación para Windows, biblioteca de clases, aplicación de consola, biblioteca de controles de Windows, biblioteca de controles Web, servicio de Windows, vacío y sitio Web.  
  
 Hay tres versiones del objeto `My.Application`, dos versiones del objeto `My.Computer` y dos versiones de `My.User` objeto; los detalles sobre estas versiones se proporcionan en las notas a pie de la tabla.  
  
|My (objeto)|Aplicación de Windows|Biblioteca de clases|Aplicación de consola|Biblioteca de controles de Windows|Biblioteca de controles Web|Servicio de Windows|Vacío|Sitio web|  
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
  
 <sup>1</sup> Windows Forms versión de `My.Application`. Deriva de la versión de la consola (vea la nota 3); agrega compatibilidad para interactuar con las ventanas de la aplicación y proporciona el modelo de aplicación Visual Basic.  
  
 versión de <sup>la biblioteca de</sup> `My.Application`. Proporciona la funcionalidad básica que necesita una aplicación: proporciona miembros para escribir en el registro de la aplicación y obtener acceso a la información de la aplicación.  
  
 <sup>3</sup> versión de la consola de `My.Application`. Deriva de la versión de la biblioteca (vea la nota 2) y agrega miembros adicionales para tener acceso a los argumentos de la línea de comandos de la aplicación e información de implementación de ClickOnce.  
  
 <sup>4</sup> versión de Windows de `My.Computer`. Deriva de la versión del servidor (vea la nota 5) y proporciona acceso a objetos útiles en un equipo cliente, como el teclado, la pantalla y el mouse.  
  
 <sup>5</sup> versión del servidor de `My.Computer`. Proporciona información básica sobre el equipo, como el nombre, el acceso al reloj, etc.  
  
 <sup>6</sup> versión de Windows de `My.User`. Este objeto está asociado a la identidad actual del subproceso.  
  
 <sup>7</sup> versión Web de `My.User`. Este objeto está asociado a la identidad del usuario de la solicitud HTTP actual de la aplicación.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Personalización de los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [My.Forms (objeto)](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.Request (objeto)](../../../visual-basic/language-reference/objects/my-request-object.md)
- [My.Response (objeto)](../../../visual-basic/language-reference/objects/my-response-object.md)
- [My.WebServices (objeto)](../../../visual-basic/language-reference/objects/my-webservices-object.md)
