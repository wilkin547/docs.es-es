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

`My` exposes only those objects required by a particular project type. For example, the `My.Forms` object is available in a Windows Forms application but not available in a console application. This topic describes which `My` objects are available in different project types.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>My in Windows Applications and Web Sites  

 `My` exposes only objects that are useful in the current project type; it suppresses objects that are not applicable. For example, the following image shows the `My` object model in a Windows Forms project.  
  
 ![Diagram that shows the My object model in a Windows Forms application.](./media/how-my-depends-on-project-type/my-object-model-windows-forms.png)  
  
 In a Web site project, `My` exposes objects that are relevant to a Web developer (such as the `My.Request` and `My.Response` objects) while suppressing objects that are not relevant (such as the `My.Forms` object). The following image shows the `My` object model in a Web site project:  
  
 ![Diagram that shows the My object model in a Web application.](./media/how-my-depends-on-project-type/my-object-model-web.png)  
  
## <a name="project-details"></a>Project Details  

 The following table shows which `My` objects are enabled by default for eight project types: Windows application, class Library, console application, Windows control library, Web control library, Windows service, empty, and Web site.  
  
 There are three versions of the `My.Application` object, two versions of the `My.Computer` object, and two versions of `My.User` object; details about these versions are given in the footnotes after the table.  
  
|My Object|Aplicación Windows|Biblioteca de clases|Aplicación de consola|Windows Control Library|Web Control Library|Servicio de Windows|Empty|Sitio web|  
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
  
 <sup>1</sup> Windows Forms version of `My.Application`. Derives from the console version (see Note 3); adds support for interacting with the application's windows and provides the Visual Basic Application model.  
  
 <sup>2</sup> Library version of `My.Application`. Provides the basic functionality needed by an application: provides members for writing to the application log and accessing application information.  
  
 <sup>3</sup> Console version of `My.Application`. Derives from the library version (see Note 2), and adds additional members for accessing the application's command-line arguments and ClickOnce deployment information.  
  
 <sup>4</sup> Windows version of `My.Computer`. Derives from the Server version (see Note 5), and provides access to useful objects on a client machine, such as the keyboard, screen, and mouse.  
  
 <sup>5</sup> Server version of `My.Computer`. Provides basic information about the computer, such as the name, access to the clock, and so on.  
  
 <sup>6</sup> Windows version of `My.User`. This object is associated with the thread's current identity.  
  
 <sup>7</sup> Web version of `My.User`. This object is associated with the user identity of the application's current HTTP request.  
  
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
