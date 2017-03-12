---
title: "End (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.End"
  - "End"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "code, salir"
  - "End (palabra clave), End (instrucciones)"
  - "End (instrucción)"
  - "ejecución, finalizar"
  - "ejecución, detener"
  - "archivos, cerrar"
  - "finalización del programa"
  - "programas, salir"
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# End (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Finaliza la ejecución inmediatamente.  
  
## Sintaxis  
  
```  
End  
```  
  
## Comentarios  
 Puede colocar en cualquier parte la instrucción `End` en un procedimiento para obligar a la aplicación completa que detenga la ejecución.  `End` cierra cualquier archivo que empiece por una instrucción `Open` y borra todas las variables de la aplicación.  La aplicación se cierra en cuanto no detecte otros programas que mantengan referencias a sus objetos y no haya código en ejecución.  
  
> [!NOTE]
>  La instrucción `End` detiene repentinamente la ejecución de código, sin invocar el método `Dispose` o `Finalize`, o ningún otro código de Visual Basic.  Se invalidan las referencias de objetos mantenidas por otros programas.  Si una instrucción `End` se encuentra dentro de un bloque `Try` o `Catch`, el control no pasa al bloque `Finally` correspondiente.  
  
 La instrucción `Stop` suspende la ejecución, pero a diferencia de `End` no cierra ningún archivo ni borra variables, a menos que se encuentre en un archivo ejecutable compilado \(.exe\).  
  
 Dado que `End` finaliza su aplicación sin tener en cuenta los recursos que podrían estar abiertos, debería intentar cerrar limpiamente antes de utilizarlo.  Por ejemplo, si su aplicación tiene formularios abiertos, debería cerrarlos antes de que el control llegue a la instrucción `End`.  
  
 Debería utilizar `End` moderadamente, y sólo cuando sea necesario detener la ejecución inmediatamente.  Las formas normales de terminar un procedimiento \([Return \(Instrucción\)](../../../visual-basic/language-reference/statements/return-statement.md) y [Exit \(Instrucción\)](../../../visual-basic/language-reference/statements/exit-statement.md)\) no sólo cierran el procedimiento limpiamente, sino que también dan al código que lo llamó la oportunidad de cerrarse limpiamente.  Por ejemplo, una aplicación de consola puede sencillamente volver \(`Return`\) del procedimiento `Main`.  
  
> [!IMPORTANT]
>  La instrucción `End` llama al método <xref:System.Environment.Exit%2A> de la clase <xref:System.Environment> en el espacio de nombres <xref:System>.  <xref:System.Environment.Exit%2A> requiere que tenga permiso `UnmanagedCode`.  De lo contrario, se genera un error <xref:System.Security.SecurityException>.  
  
 Cuando va seguido por una palabra clave adicional, [End \<palabra clave\> \(Instrucción\)](../../../visual-basic/language-reference/statements/end-keyword-statement.md) indica el final de la definición del procedimiento o bloque correspondientes.  Por ejemplo, `End Function` finaliza la definición de un procedimiento `Function`.  
  
## Ejemplo  
 El ejemplo siguiente utiliza la instrucción `End` para terminar la ejecución del código si el usuario lo solicita.  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVersHelp60Controls/Form1.vb#64)]  
  
## Notas para desarrolladores de dispositivos Smart Device  
 No se admite esta instrucción.  
  
## Vea también  
 <xref:System.Security.Permissions.SecurityPermissionFlag>   
 [Stop \(Instrucción\)](../../../visual-basic/language-reference/statements/stop-statement.md)   
 [End \<palabra clave\> \(Instrucción\)](../../../visual-basic/language-reference/statements/end-keyword-statement.md)