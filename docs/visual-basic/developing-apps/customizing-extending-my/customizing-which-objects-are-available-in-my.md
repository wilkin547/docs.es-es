---
title: Personalizar los objetos que están disponibles en My (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: caddad463f7c525c8b715d70f49bf8bebcc7cfbd
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701267"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Personalizar los objetos que están disponibles en My (Visual Basic)

En este tema se describe cómo puede controlar qué objetos `My` están habilitados estableciendo la constante de compilación condicional `_MYTYPE` del proyecto. El entorno de desarrollo integrado (IDE) de Visual Studio mantiene la constante de compilación condicional `_MYTYPE` para un proyecto sincronizado con el tipo del proyecto.  
  
## <a name="predefined-_mytype-values"></a>Valores predefinidos \_MYTYPE  

Debe usar la opción del compilador `/define` para establecer la constante de compilación condicional `_MYTYPE`. Al especificar su propio valor para la constante `_MYTYPE`, debe incluir el valor de cadena en las secuencias de la barra diagonal inversa/comilla (\\ "). Por ejemplo, podría usar:  
  
```console  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 En esta tabla se muestra el valor de la constante de compilación condicional `_MYTYPE` está establecida en para varios tipos de proyecto.  
  
|Tipo de proyecto|@no__t: valor de 0MYTYPE|  
|------------------|--------------------|  
|Biblioteca de clases|Windows|  
|Aplicación de consola|Console|  
|Web|Web|  
|Biblioteca de controles Web|WebControl|  
|Aplicación Windows|WindowsForms|  
|Aplicación para Windows, al iniciar con @no__t personalizado-0|"WindowsFormsWithCustomSubMain"|  
|Biblioteca de controles de Windows|Windows|  
|Servicio de Windows|Console|  
|Empty|Vacía|  
  
> [!NOTE]
> Todas las comparaciones de cadenas de compilación condicional distinguen mayúsculas de minúsculas, independientemente de cómo se establezca la instrucción `Option Compare`.  
  
## <a name="dependent-_my-compilation-constants"></a>Constantes de compilación dependientes de \_MY  

A su vez, la constante de compilación condicional `_MYTYPE` controla los valores de varias otras constantes de compilación `_MY`:  
  
|@NO__T 0MYTYPE|@NO__T 0MYAPPLICATIONTYPE|@NO__T 0MYCOMPUTERTYPE|@NO__T 0MYFORMS|@NO__T 0MYUSERTYPE|@NO__T 0MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|Console|Console|Windows|Sin definir|Windows|true|  
|Personal|Sin definir|Sin definir|Sin definir|Sin definir|Sin definir|  
|Vacía|Sin definir|Sin definir|Sin definir|Sin definir|Sin definir|  
|Web|Sin definir|Web|false|Web|false|  
|WebControl|Sin definir|Web|false|Web|true|  
|"Windows" o ""|Windows|Windows|Sin definir|Windows|true|  
|WindowsForms|WindowsForms|Windows|true|Windows|true|  
|"WindowsFormsWithCustomSubMain"|Console|Windows|true|Windows|true|  
  
 De forma predeterminada, las constantes de compilación condicional sin definir se resuelven en `FALSE`. Puede especificar valores para las constantes no definidas al compilar el proyecto para invalidar el comportamiento predeterminado.  
  
> [!NOTE]
> Cuando `_MYTYPE` se establece en "Custom", el proyecto contiene el espacio de nombres `My`, pero no contiene ningún objeto. Sin embargo, si se establece `_MYTYPE` en "Empty", se impide que el compilador agregue el espacio de nombres `My` y sus objetos.  
  
 En esta tabla se describen los efectos de los valores predefinidos de las constantes de compilación `_MY`.  
  
|Constante|Significado|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Habilita `My.Application`, si la constante es "Console", "Windows" o "WindowsForms":<br /><br /> -La versión "Console" deriva de <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. y tiene menos miembros que la versión "Windows".<br />-La versión "Windows" deriva de @no__t -0. y tiene menos miembros que la versión "WindowsForms".<br />-La versión "WindowsForms" de `My.Application` deriva de <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Si la constante `TARGET` se define como "winexe", la clase incluye un método `Sub Main`.|  
|`_MYCOMPUTERTYPE`|Habilita `My.Computer`, si la constante es "Web" o "Windows":<br /><br /> -La versión "Web" deriva de <xref:Microsoft.VisualBasic.Devices.ServerComputer> y tiene menos miembros que la versión "Windows".<br />-La versión "Windows" de `My.Computer` deriva de <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Habilita `My.Forms`, si la constante es `TRUE`.|  
|`_MYUSERTYPE`|Habilita `My.User`, si la constante es "Web" o "Windows":<br /><br /> -La versión "Web" de `My.User` está asociada a la identidad del usuario de la solicitud HTTP actual.<br />-La versión "Windows" de `My.User` está asociada a la entidad de seguridad actual del subproceso.|  
|`_MYWEBSERVICES`|Habilita `My.WebServices`, si la constante es `TRUE`.|  
|`_MYTYPE`|Habilita `My.Log`, `My.Request` y `My.Response`, si la constante es "Web".|  
  
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
