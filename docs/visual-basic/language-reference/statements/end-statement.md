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
ms.openlocfilehash: fe17a82662c4014069c77f2da76723a051ab9084
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404711"
---
# <a name="end-statement"></a>End (Instrucción)
Finaliza la ejecución inmediatamente.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
End  
```  
  
## <a name="remarks"></a>Observaciones  
 Puede colocar la `End` instrucción en cualquier parte de un procedimiento para obligar a que toda la aplicación deje de ejecutarse. `End`cierra los archivos abiertos con una `Open` instrucción y borra todas las variables de la aplicación. La aplicación se cierra en cuanto no hay ningún otro programa que contenga referencias a sus objetos y no se está ejecutando ningún código.  
  
> [!NOTE]
> La `End` instrucción detiene la ejecución del código repentinamente y no invoca el `Dispose` `Finalize` método o, ni ningún otro código de Visual Basic. Se invalidan las referencias de objeto mantenidas por otros programas. Si `End` se encuentra una instrucción dentro de `Try` un `Catch` bloque o, el control no pasa al `Finally` bloque correspondiente.  
  
 La `Stop` instrucción suspende la ejecución, pero, `End` a diferencia de, no cierra ningún archivo ni borra ninguna variable, a menos que se encuentre en un archivo ejecutable (. exe) compilado.  
  
 Dado que `End` finaliza la aplicación sin tener que ocuparse de los recursos que puedan estar abiertos, debe intentar cerrarlo correctamente antes de usarlo. Por ejemplo, si la aplicación tiene algún formulario abierto, debe cerrarlo antes de que el control alcance la `End` instrucción.  
  
 Debería usar con `End` moderación y solo cuando necesite detenerse inmediatamente. Las formas normales de finalizar un procedimiento ([instrucción return](return-statement.md) y de [salida](exit-statement.md)) no solo cierran el procedimiento correctamente, sino que también proporcionan al código de llamada la oportunidad de cerrarse sin problemas. Por ejemplo, una aplicación de consola puede simplemente `Return` del `Main` procedimiento.  
  
> [!IMPORTANT]
> La `End` instrucción llama al <xref:System.Environment.Exit%2A> método de la <xref:System.Environment> clase en el <xref:System> espacio de nombres. <xref:System.Environment.Exit%2A>requiere que tenga `UnmanagedCode` permiso. Si no lo hace, <xref:System.Security.SecurityException> se produce un error.  
  
 Cuando va seguido de una palabra clave adicional, la [ \<keyword> instrucción end](end-keyword-statement.md) delimita el final de la definición del procedimiento o bloque adecuado. Por ejemplo, `End Function` finaliza la definición de un `Function` procedimiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la `End` instrucción para finalizar la ejecución del código si el usuario lo solicita.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Notas para desarrolladores de Smart Device  
 Esta instrucción no se admite.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Instrucción Stop](stop-statement.md)
- [End ( \<keyword> instrucción)](end-keyword-statement.md)
