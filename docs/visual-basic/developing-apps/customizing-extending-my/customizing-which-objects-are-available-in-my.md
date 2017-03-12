---
title: "Personalizar los objetos que est&#225;n disponibles en My (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My (espacio de nombres)"
  - "My (espacio de nombres), personalizar"
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Personalizar los objetos que est&#225;n disponibles en My (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este tema describe cómo se puede controlar qué objetos `My` están habilitados estableciendo la constante de compilación condicional `_MYTYPE` de su proyecto.  El entorno de desarrollo integrado \(IDE\) de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] mantiene la constante de compilación condicional `_MYTYPE` para un proyecto en sincronización con el tipo del proyecto.  
  
## Valores predefinidos de \_MYTYPE  
 Debe utilizar la opción `/define` del compilador para establecer la constante de compilación condicional `_MYTYPE`.  Al especificar su propio valor para la constante `_MYTYPE`, debe incluir el valor de cadena en secuencias de barra diagonal inversa\/comillas \(\\"\).  Por ejemplo, podría utilizar:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 Esta tabla muestra en qué está establecida la constante de compilación condicional `_MYTYPE` para varios tipos de proyecto.  
  
|Tipo de proyecto|Valor de \_MYTYPE|  
|----------------------|-----------------------|  
|Biblioteca de clases|"Windows"|  
|Aplicación de consola|"Console"|  
|Web|"Web"|  
|Biblioteca de controles Web|"WebControl"|  
|Aplicación Windows|"WindowsForms"|  
|Aplicación para Windows, al iniciarse con un procedimiento `Sub Main` personalizado|"WindowsFormsWithCustomSubMain"|  
|Biblioteca de controles de Windows|"Windows"|  
|Servicio de Windows|"Console"|  
|Vacío|"Empty"|  
  
> [!NOTE]
>  Todas las comparaciones de cadenas de compilación condicional distinguen entre mayúsculas y minúsculas, sin tener en cuenta en qué está establecida la instrucción `Option Compare`.  
  
## Constantes dependientes de compilación de \_MY  
 La constante de compilación condicional `_MYTYPE`, a su vez, controla los valores de varias otras constantes de compilación `_MY`:  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|No definido|"Windows"|TRUE|  
|"Custom"|No definido|No definido|No definido|No definido|No definido|  
|"Empty"|No definido|No definido|No definido|No definido|No definido|  
|"Web"|No definido|"Web"|FALSE|"Web"|FALSE|  
|"WebControl"|No definido|"Web"|FALSE|"Web"|TRUE|  
|"Windows" o ""|"Windows"|"Windows"|No definido|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|TRUE|"Windows"|TRUE|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|TRUE|"Windows"|TRUE|  
  
 De manera predeterminada, las constantes de compilación condicional indefinidas se resuelven como `FALSE`.  Puede especificar los valores para las constantes indefinidas al compilar su proyecto para que reemplacen el comportamiento predeterminado.  
  
> [!NOTE]
>  Cuando `_MYTYPE` está establecida en "Custom", el proyecto contiene el espacio de nombres `My`, pero no contiene ningún objeto.  Sin embargo, estableciendo `_MYTYPE` en "Empty" se evita que el compilador agregue el espacio de nombres `My` y sus objetos.  
  
 Esta tabla describe los efectos de los valores predefinidos de las constantes de compilación `_MY`.  
  
|Constante|Significado|  
|---------------|-----------------|  
|`_MYAPPLICATIONTYPE`|Habilita `My.Application`, si la constante es "Console", Windows" o "WindowsForms":<br /><br /> -   La versión de "Console" deriva de <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> y tiene menos miembros que la versión de "Windows".<br />-   La versión de "Windows" deriva de <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> y tiene menos miembros que la versión de "WindowsForms".<br />-   La versión de "WindowsForms" de `My.Application` deriva de <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>.  Si la constante `TARGET` está definida para que sea "winexe", la clase incluye un método `Sub Main`.|  
|`_MYCOMPUTERTYPE`|Habilita `My.Computer` si la constante es "Web" o "Windows":<br /><br /> -   La versión de "Web" deriva de <xref:Microsoft.VisualBasic.Devices.ServerComputer> y tiene menos miembros que la versión de "Windows".<br />-   La versión de "Windows" de `My.Computer` deriva de <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Habilita `My.Forms` si la constante es `TRUE`.|  
|`_MYUSERTYPE`|Habilita `My.User` si la constante es "Web" o "Windows":<br /><br /> -   La versión de "Web" de `My.User` se asocia a la identidad del usuario de la solicitud HTTP actual.<br />-   La versión de "Windows" de `My.User` se asocia a la entidad de seguridad actual del subproceso.|  
|`_MYWEBSERVICES`|Habilita `My.WebServices` si la constante es `TRUE`.|  
|`_MYTYPE`|Habilita `My.Log`, `My.Request` y `My.Response`, si la constante es "Web".|  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Cómo My depende del tipo de proyecto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)   
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)   
 [My.Forms \(Objeto\)](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [My.Request \(Objeto\)](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [My.Response \(Objeto\)](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [My.WebServices \(Objeto\)](../../../visual-basic/language-reference/objects/my-webservices-object.md)