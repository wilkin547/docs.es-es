---
title: Personalizar los objetos que están disponibles en My
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: 0387aca08e3a31b0a2045369919894d88caf5b76
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330326"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Personalizar los objetos que están disponibles en My (Visual Basic)

En este tema se describe cómo puede controlar qué objetos `My` se habilitan estableciendo la constante de compilación condicional `_MYTYPE` del proyecto. El entorno de desarrollo integrado (IDE) de Visual Studio mantiene la constante de compilación condicional `_MYTYPE` para un proyecto sincronizado con el tipo del proyecto.  
  
## <a name="predefined-_mytype-values"></a>Valores \_MYTYPE predefinidos  

Debe utilizar la opción del compilador `/define` para establecer la constante de compilación condicional `_MYTYPE`. Al especificar su propio valor para la constante `_MYTYPE`, debe incluir el valor de cadena en las secuencias de la barra diagonal inversa/comilla (\\"). Por ejemplo, podría usar:  
  
```console  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 En esta tabla se muestra cómo se establece la constante de compilación condicional `_MYTYPE` para varios tipos de proyecto.  
  
|Tipo de proyecto|Valor \_MYTYPE|  
|------------------|--------------------|  
|Biblioteca de clases|"Windows"|  
|Aplicación de consola|"Console"|  
|Web|"Web"|  
|Biblioteca de controles web|"WebControl"|  
|Aplicación Windows|"WindowsForms"|  
|Aplicación para Windows, al iniciar con un elemento `Sub Main` personalizado|"WindowsFormsWithCustomSubMain"|  
|Biblioteca de controles de Windows|"Windows"|  
|Servicio de Windows|"Console"|  
|Empty|"Empty"|  
  
> [!NOTE]
> Todas las comparaciones de cadenas de compilación condicional distinguen entre mayúsculas y minúsculas, independientemente de cómo se establezca la instrucción `Option Compare`.  
  
## <a name="dependent-_my-compilation-constants"></a>Constantes de compilación \_MY dependientes  

A su vez, la constante de compilación condicional `_MYTYPE` controla los valores de varias otras constantes de compilación `_MY`:  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|Sin definir|"Windows"|true|  
|"Custom"|Sin definir|Sin definir|Sin definir|Sin definir|Sin definir|  
|"Empty"|Sin definir|Sin definir|Sin definir|Sin definir|Sin definir|  
|"Web"|Sin definir|"Web"|false|"Web"|false|  
|"WebControl"|Sin definir|"Web"|false|"Web"|true|  
|"Windows" o ""|"Windows"|"Windows"|Sin definir|"Windows"|true|  
|"WindowsForms"|"WindowsForms"|"Windows"|true|"Windows"|true|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|true|"Windows"|true|  
  
 De forma predeterminada, las constantes de compilación condicional sin definir se resuelven en `FALSE`. Puede especificar valores para las constantes no definidas al compilar el proyecto para reemplazar el comportamiento predeterminado.  
  
> [!NOTE]
> Si `_MYTYPE` se establece en "Custom", el proyecto contiene el espacio de nombres `My`, pero no contiene ningún objeto. Sin embargo, si `_MYTYPE` se establece en "Empty", se impide que el compilador agregue el espacio de nombres `My` y sus objetos.  
  
 En esta tabla se describen los efectos de los valores predefinidos de las constantes de compilación `_MY`.  
  
|Constante|Significado|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Habilita `My.Application`, si la constante es "Console", "Windows" o "WindowsForms":<br /><br /> - La versión "Console" deriva de <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>; tiene menos miembros que la versión "Windows".<br />- La versión "Windows" deriva de <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>; tiene menos miembros que la versión "WindowsForms".<br />- La versión "WindowsForms" de `My.Application` deriva de <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Si la constante `TARGET` se define como "winexe", la clase incluye un método `Sub Main`.|  
|`_MYCOMPUTERTYPE`|Habilita `My.Computer`, si la constante es "Web" o "Windows":<br /><br /> - La versión "Web" deriva de <xref:Microsoft.VisualBasic.Devices.ServerComputer>; tiene menos miembros que la versión "Windows".<br />- La versión "Windows" de `My.Computer` deriva de <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Habilita `My.Forms`, si la constante es `TRUE`.|  
|`_MYUSERTYPE`|Habilita `My.User`, si la constante es "Web" o "Windows":<br /><br /> - La versión "Web" de `My.User` está asociada a la identidad del usuario de la solicitud HTTP actual.<br />- La versión "Windows" de `My.User` está asociada a la entidad de seguridad actual del subproceso.|  
|`_MYWEBSERVICES`|Habilita `My.WebServices`, si la constante es `TRUE`.|  
|`_MYTYPE`|Habilita `My.Log`, `My.Request` y `My.Response`, si la constante es "Web".|  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Cómo My depende del tipo de proyecto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [My.Forms (objeto)](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.Request (objeto)](../../../visual-basic/language-reference/objects/my-request-object.md)
- [My.Response (objeto)](../../../visual-basic/language-reference/objects/my-response-object.md)
- [My.WebServices (objeto)](../../../visual-basic/language-reference/objects/my-webservices-object.md)
