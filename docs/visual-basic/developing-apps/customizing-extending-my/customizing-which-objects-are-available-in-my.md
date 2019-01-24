---
title: Personalizar los objetos que están disponibles en My (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: caa9c2cadb9194161756f89b5acb16da0a955485
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543726"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Personalizar los objetos que están disponibles en My (Visual Basic)
Este tema describe cómo puede controlar qué `My` objetos se habilitan estableciendo el proyecto `_MYTYPE` constante de compilación condicional. El entorno de desarrollo integrado (IDE) de Visual Studio mantiene el `_MYTYPE` constante de compilación condicional para un proyecto en sincronización con el tipo del proyecto.  
  
## <a name="predefined-mytype-values"></a>Valores predefinidos de _MYTYPE  
 Debe usar el `/define` opción del compilador para establecer el `_MYTYPE` constante de compilación condicional. Al especificar su propio valor para el `_MYTYPE` constante, debe incluir el valor de cadena en la barra diagonal inversa/comillas (\\") las secuencias. Por ejemplo, podría utilizar:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 Esta tabla muestra lo que el `_MYTYPE` constante de compilación condicional se establece en para varios tipos de proyecto.  
  
|Tipo de proyecto|Valor _MYTYPE|  
|------------------|--------------------|  
|Biblioteca de clases|"Windows"|  
|Aplicación de consola|"Consola"|  
|Web|"Web"|  
|Biblioteca de controles Web|"WebControl"|  
|Aplicación Windows|"WindowsForms"|  
|Aplicación de Windows, cuando se inicia con personalizado `Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Biblioteca de controles de Windows|"Windows"|  
|Servicio de Windows|"Consola"|  
|Empty|'Empty'|  
  
> [!NOTE]
>  Todas las comparaciones de cadenas de compilación condicional distinguen mayúsculas de minúsculas, con independencia `Option Compare` se establece la instrucción.  
  
## <a name="dependent-my-compilation-constants"></a>Constantes de compilación _MY dependientes  
 El `_MYTYPE` constante de compilación condicional, a su vez, controla los valores de los otros `_MY` constantes de compilación:  
  
|_MYTYPE|_MYAPPLICATIONTYPE|_MYCOMPUTERTYPE|_MYFORMS|_MYUSERTYPE|_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Consola"|"Consola"|"Windows"|Sin definir|"Windows"|true|  
|"Custom"|Sin definir|Sin definir|Sin definir|Sin definir|Sin definir|  
|'Empty'|Sin definir|Sin definir|Sin definir|Sin definir|Sin definir|  
|"Web"|Sin definir|"Web"|false|"Web"|false|  
|"WebControl"|Sin definir|"Web"|false|"Web"|true|  
|"Windows" o ""|"Windows"|"Windows"|Sin definir|"Windows"|true|  
|"WindowsForms"|"WindowsForms"|"Windows"|true|"Windows"|true|  
|"WindowsFormsWithCustomSubMain"|"Consola"|"Windows"|true|"Windows"|true|  
  
 De forma predeterminada, las constantes de compilación condicional indefinidas resuelven a `FALSE`. Puede especificar valores para las constantes no definidos al compilar el proyecto para invalidar el comportamiento predeterminado.  
  
> [!NOTE]
>  Cuando `_MYTYPE` está establecido en "Custom", el proyecto contiene el `My` espacio de nombres, pero no contiene ningún objeto. Sin embargo, establecer `_MYTYPE` a "Vacío" evita que el compilador agrega el `My` espacio de nombres y sus objetos.  
  
 Esta tabla describen los efectos de los valores predefinidos de la `_MY` constantes de compilación.  
  
|Constante|Significado|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Permite `My.Application`, si la constante es "Console", Windows, "o"WindowsForms":<br /><br /> -La versión de "Console" deriva de <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. y tiene menos miembros que la versión de "Windows".<br />-La versión de "Windows" deriva de <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>y tiene menos miembros que la versión de "WindowsForms".<br />-La versión de "WindowsForms" de `My.Application` deriva <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Si el `TARGET` constante se define como "winexe", a continuación, la clase incluye un `Sub Main` método.|  
|`_MYCOMPUTERTYPE`|Permite `My.Computer`, si la constante es "Web" o "Windows":<br /><br /> -La versión de "Web" se deriva de <xref:Microsoft.VisualBasic.Devices.ServerComputer>, y tiene menos miembros que la versión de "Windows".<br />-La versión de "Windows" de `My.Computer` deriva <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Permite `My.Forms`, si la constante es `TRUE`.|  
|`_MYUSERTYPE`|Permite `My.User`, si la constante es "Web" o "Windows":<br /><br /> -La versión de "Web" de `My.User` está asociado con la identidad del usuario de la solicitud HTTP actual.<br />-La versión de "Windows" de `My.User` está asociado con la entidad de seguridad del subproceso actual.|  
|`_MYWEBSERVICES`|Permite `My.WebServices`, si la constante es `TRUE`.|  
|`_MYTYPE`|Permite `My.Log`, `My.Request`, y `My.Response`, si la constante es "Web".|  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Cómo My depende del tipo de proyecto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [My.Forms (objeto)](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.Request (objeto)](../../../visual-basic/language-reference/objects/my-request-object.md)
- [My.Response (objeto)](../../../visual-basic/language-reference/objects/my-response-object.md)
- [My.WebServices (objeto)](../../../visual-basic/language-reference/objects/my-webservices-object.md)
