---
title: Personalizar los objetos que están disponibles en My (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 669641a2b6ecbf988f6cad68acf52c5561b32515
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Personalizar los objetos que están disponibles en My (Visual Basic)
Este tema describe cómo puede controlar qué `My` objetos se habilitan estableciendo el proyecto `_MYTYPE` constante de compilación condicional. El entorno de desarrollo integrado (IDE) de Visual Studio mantiene el `_MYTYPE` constante de compilación condicional para un proyecto en sincronización con el tipo del proyecto.  
  
## <a name="predefined-mytype-values"></a>Valores predefinidos de _MYTYPE  
 Debe utilizar el `/define` opción del compilador para establecer el `_MYTYPE` constante de compilación condicional. Al especificar su propio valor para la `_MYTYPE` constante, debe incluir el valor de cadena en la barra diagonal inversa/comillas (\\") las secuencias. Por ejemplo, podría utilizar:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 Esta tabla muestra lo que hace el `_MYTYPE` constante de compilación condicional se establece en para varios tipos de proyecto.  
  
|Tipo de proyecto|Valor _MYTYPE|  
|------------------|--------------------|  
|Biblioteca de clases|"Windows"|  
|Aplicación de consola|"Consola"|  
|Web|"Web"|  
|Biblioteca de controles Web|"WebControl"|  
|Aplicación Windows|"WindowsForms"|  
|Aplicación de Windows, al iniciarse con personalizado `Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Biblioteca de controles de Windows|"Windows"|  
|Servicio de Windows|"Consola"|  
|Empty|"Vacío"|  
  
> [!NOTE]
>  Todas las comparaciones de cadenas de compilación condicional distinguen mayúsculas de minúsculas, independientemente de cómo `Option Compare` instrucción se establece.  
  
## <a name="dependent-my-compilation-constants"></a>Constantes de compilación de _MY dependientes  
 El `_MYTYPE` constante de compilación condicional, a su vez, controla los valores de los otros `_MY` constantes de compilación:  
  
|_MYTYPE|_MYAPPLICATIONTYPE|_MYCOMPUTERTYPE|_MYFORMS|_MYUSERTYPE|_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Consola"|"Consola"|"Windows"|Sin definir|"Windows"|true|  
|"Custom"|Sin definir|Sin definir|Sin definir|Sin definir|Sin definir|  
|"Vacío"|Sin definir|Sin definir|Sin definir|Sin definir|Sin definir|  
|"Web"|Sin definir|"Web"|false|"Web"|false|  
|"WebControl"|Sin definir|"Web"|false|"Web"|true|  
|"Windows" o ""|"Windows"|"Windows"|Sin definir|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|true|"Windows"|true|  
|"WindowsFormsWithCustomSubMain"|"Consola"|"Windows"|true|"Windows"|true|  
  
 De forma predeterminada, resuelven sin definir constantes de compilación condicional en `FALSE`. Puede especificar valores para las constantes sin definir cuando se compila el proyecto para invalidar el comportamiento predeterminado.  
  
> [!NOTE]
>  Cuando `_MYTYPE` se establece en "Custom", el proyecto contiene el `My` espacio de nombres, pero no contiene ningún objeto. Sin embargo, establecer `_MYTYPE` a "Vacío" impide que el compilador agrega las `My` espacio de nombres y sus objetos.  
  
 Esta tabla describen los efectos de los valores predefinidos de la `_MY` constantes de compilación.  
  
|Constante|Significado|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Permite `My.Application`, si la constante es "Ventanas de la consola,", "o"WindowsForms":<br /><br /> -La versión de "Console" deriva de <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. y tiene menos miembros que la versión de "Windows".<br />-La versión de "Windows" deriva de <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>y tiene menos miembros que la versión de "WindowsForms".<br />-La versión de "WindowsForms" de `My.Application` deriva de <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Si el `TARGET` constante se define como "winexe", a continuación, la clase incluye una `Sub Main` método.|  
|`_MYCOMPUTERTYPE`|Permite `My.Computer`, si la constante es "Web" o "Windows":<br /><br /> -La versión de "Web" deriva de <xref:Microsoft.VisualBasic.Devices.ServerComputer>, y tiene menos miembros que la versión de "Windows".<br />-La versión de "Windows" `My.Computer` deriva de <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Permite `My.Forms`, si la constante es `TRUE`.|  
|`_MYUSERTYPE`|Permite `My.User`, si la constante es "Web" o "Windows":<br /><br /> -La versión de "Web" de `My.User` está asociado a la identidad del usuario de la solicitud HTTP actual.<br />-La versión de "Windows" `My.User` está asociado a la entidad de seguridad actual del subproceso.|  
|`_MYWEBSERVICES`|Permite `My.WebServices`, si la constante es `TRUE`.|  
|`_MYTYPE`|Permite `My.Log`, `My.Request`, y `My.Response`, si la constante es "Web".|  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.Logging.Log>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [Cómo My depende del tipo de proyecto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [My.Forms (objeto)](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.Request (objeto)](../../../visual-basic/language-reference/objects/my-request-object.md)  
 [My.Response (objeto)](../../../visual-basic/language-reference/objects/my-response-object.md)  
 [My.WebServices (objeto)](../../../visual-basic/language-reference/objects/my-webservices-object.md)
