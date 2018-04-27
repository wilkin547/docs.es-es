---
title: -errorreport
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dc321f7f927d68a9f270076640cbc6d31d2f6d5
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="-errorreport"></a>-errorreport
Especifica cómo el compilador de Visual Basic debería notificar errores internos del compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a>Comentarios  
 Esta opción proporciona una manera cómoda para notificar un error interno del compilador de Visual Basic (ICE) al equipo de Visual Basic en Microsoft. De forma predeterminada, el compilador no envía ninguna información a Microsoft. Sin embargo, si se produce un error interno del compilador, esta opción le permite notificar el error a Microsoft. Esta información le ayudará a los ingenieros de Microsoft a identificar la causa y puede ayudar a mejorar la próxima versión de Visual Basic.  
  
 Capacidad de un usuario para enviar informes depende de los permisos de directiva de equipo y de usuario.  
  
 En la tabla siguiente se resume el efecto de la `-errorreport` opción.  
  
|Opción|Comportamiento|  
|---|---|  
|`prompt`|Si se produce un error interno del compilador, aparece un cuadro de diálogo para que pueda ver los datos exactos que recogidos por el compilador. Puede determinar si hay cualquier información confidencial en el informe de errores y tomar una decisión sobre si se envía a Microsoft. Si decide enviarlo, y la configuración de directiva de equipo y de usuario lo permite, el compilador envía los datos a Microsoft.|  
|`queue`|Pone en cola el informe de error. Cuando inicia una sesión con privilegios de administrador, puede notificar los errores desde la última vez que se ha iniciado sesión (no se le pedirá que envíe informes de errores más de una vez cada tres días). Éste es el comportamiento predeterminado cuando la `-errorreport` no se especifica la opción.|  
|`send`|Si se produce un error interno del compilador y la configuración de directiva de equipo y de usuario lo permite, el compilador envía los datos a Microsoft.<br /><br /> La opción `-errorreport:send` intenta enviar automáticamente información de errores a Microsoft. Esta opción depende del registro. Para obtener más información acerca de cómo establecer los valores apropiados en el registro, consulte [cómo activar informe de errores automático en herramientas de línea de comandos de Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695).|  
|`none`|Si se produce un error interno del compilador, no se recopila o envía a Microsoft.|  
  
 El compilador envía datos que incluyen la pila en el momento del error, que normalmente incluye algún código fuente. Si `-errorreport` se utiliza con la [- bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opción, se envía el archivo de código fuente.  
  
 Esta opción se utiliza con la [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opción, porque permite que los ingenieros de Microsoft a más fácilmente reproducen el error.  
  
> [!NOTE]
>  El `-errorreport` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente intenta compilar `T2.vb`, y si el compilador encuentra un error interno del compilador, solicita si desea enviar el informe de errores a Microsoft.  
  
```  
vbc -errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
