---
title: End (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: 864ac5ef1713f8ffa93c18accede8ecd5b3b7a8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604437"
---
# <a name="end-statement"></a>End (Instrucción)
Finaliza la ejecución inmediatamente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
End  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede colocar el `End` instrucción en cualquier parte de un procedimiento para forzar la aplicación completa para detener la ejecución. `End` cierra los archivos abiertos con un `Open` instrucción y borra todas las variables de la aplicación. La aplicación se cierra en cuanto no hay ningún otro programa que contiene referencias a sus objetos y se está ejecutando ninguna de su código.  
  
> [!NOTE]
>  El `End` instrucción detiene la ejecución de código repentinamente y no invoca el `Dispose` o `Finalize` (método), o cualquier otro código de Visual Basic. Se invalidan las referencias a objetos mantenidas por otros programas. Si un `End` instrucción se encuentra dentro de un `Try` o `Catch` bloque de control no pasa a la correspondiente `Finally` bloque.  
  
 El `Stop` instrucción suspende la ejecución, pero, a diferencia `End`, no cierra ningún archivo ni borra variables, a menos que se encuentra en un archivo ejecutable compilado (.exe).  
  
 Porque `End` finaliza la aplicación sin prestar atención a los recursos que pueden estar abiertos, debería intentar cerrarse limpiamente antes de usarlo. Por ejemplo, si la aplicación tiene formularios abiertos, debe cerrarlos antes de control alcanza la `End` instrucción.  
  
 Debe usar `End` con moderación y solo cuando sea necesario detener inmediatamente. Lo normal para terminar un procedimiento ([instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md) y [instrucción Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) no sólo cierran el procedimiento limpiamente sino que también dan el código que realiza la llamada la oportunidad de cerrarse limpiamente. Una aplicación de consola, por ejemplo, puede simplemente `Return` desde el `Main` procedimiento.  
  
> [!IMPORTANT]
>  El `End` instrucción llama el <xref:System.Environment.Exit%2A> método de la <xref:System.Environment> clase en el <xref:System> espacio de nombres. <xref:System.Environment.Exit%2A> requiere que haya `UnmanagedCode` permiso. Si no, un <xref:System.Security.SecurityException> se produce el error.  
  
 Cuando va seguido de una palabra clave adicional, [final \<palabra clave > instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delimita el final de la definición del procedimiento adecuado o bloque. Por ejemplo, `End Function` termina la definición de un `Function` procedimiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `End` instrucción para finalizar la ejecución de código si el usuario lo solicita.  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a>Notas de desarrollador de Smart Device  
 No se admite esta instrucción.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Security.Permissions.SecurityPermissionFlag>  
 [Stop (instrucción)](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [End \<palabra clave > instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
