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
ms.openlocfilehash: cb2fb4abb21b7b9c6575cec4aca1374f63687607
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343721"
---
# <a name="end-statement"></a>End (Instrucción)
Finaliza la ejecución inmediatamente.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
End  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede colocar la instrucción `End` en cualquier parte de un procedimiento para obligar a que toda la aplicación deje de ejecutarse. `End` cierra los archivos abiertos con una instrucción `Open` y borra todas las variables de la aplicación. La aplicación se cierra en cuanto no hay ningún otro programa que contenga referencias a sus objetos y no se está ejecutando ningún código.  
  
> [!NOTE]
> La instrucción `End` detiene la ejecución del código repentinamente y no invoca el `Dispose` ni `Finalize` método, ni ningún otro código de Visual Basic. Se invalidan las referencias de objeto mantenidas por otros programas. Si se encuentra una instrucción `End` dentro de un bloque `Try` o `Catch`, el control no pasa al bloque de `Finally` correspondiente.  
  
 La instrucción `Stop` suspende la ejecución, pero a diferencia de `End`, no cierra ningún archivo ni borra ninguna variable, a menos que se encuentre en un archivo ejecutable (. exe) compilado.  
  
 Dado que `End` finaliza la aplicación sin tener que ocuparse de los recursos que puedan estar abiertos, debe intentar cerrarlo correctamente antes de usarlo. Por ejemplo, si la aplicación tiene algún formulario abierto, debe cerrarlo antes de que el control alcance la instrucción `End`.  
  
 Debería usar `End` moderadamente y solo cuando necesite detenerse inmediatamente. Las formas normales de finalizar un procedimiento ([instrucción return](../../../visual-basic/language-reference/statements/return-statement.md) y de [salida](../../../visual-basic/language-reference/statements/exit-statement.md)) no solo cierran el procedimiento correctamente, sino que también proporcionan al código de llamada la oportunidad de cerrarse sin problemas. Por ejemplo, una aplicación de consola puede `Return` del procedimiento `Main`.  
  
> [!IMPORTANT]
> La instrucción `End` llama al método <xref:System.Environment.Exit%2A> de la clase <xref:System.Environment> en el espacio de nombres <xref:System>. <xref:System.Environment.Exit%2A> requiere que tenga `UnmanagedCode` permiso. Si no lo hace, se produce un error de <xref:System.Security.SecurityException>.  
  
 Cuando va seguido de una palabra clave adicional, [End \<palabra clave > instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md) define el final de la definición del procedimiento o bloque adecuado. Por ejemplo, `End Function` finaliza la definición de un procedimiento `Function`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la instrucción `End` para finalizar la ejecución del código si el usuario lo solicita.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Notas para desarrolladores de Smart Device  
 Esta instrucción no se admite.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Stop (instrucción)](../../../visual-basic/language-reference/statements/stop-statement.md)
- [End \<palabra clave > instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
