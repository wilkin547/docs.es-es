---
title: "Error (Instrucci&#243;n) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.error"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Error (palabra clave)"
  - "Error (instrucción)"
  - "Error (instrucción), sintaxis"
  - "errores [Visual Basic], simular"
  - "errores en tiempo de ejecución, códigos"
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Error (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Simula un error generado.  
  
## Sintaxis  
  
```  
Error errornumber  
```  
  
## Elementos  
 `errornumber`  
 Obligatorio.  Puede ser cualquier número de error válido.  
  
## Comentarios  
 La instrucción `Error` se incluye a efectos de compatibilidad con versiones anteriores.  En el nuevo código, especialmente al crear objetos, utilice el método `Raise` del objeto `Err` para generar errores en tiempo de ejecución.  
  
 Si `errornumber` está definido, la instrucción `Error` realiza una llamada al controlador del error después de haber asignado a las propiedades del objeto `Err` los siguientes valores predeterminados:  
  
|Propiedad.|Valor|  
|----------------|-----------|  
|`Number`|Valor especificado como argumento de la instrucción `Error`.  Puede ser cualquier número de error válido.|  
|`Source`|Nombre del proyecto de Visual Basic actual.|  
|`Description`|Expresión de tipo String \(cadena\) correspondiente al valor devuelto por la función `Error` para el argumento `Number` especificado, si existe esa cadena.  Si la cadena no existe, `Description` contiene una cadena de longitud cero \(""\).|  
|`HelpFile`|El nombre completo con unidad, ruta de acceso y nombre de archivo del archivo de Ayuda de Visual Basic.|  
|`HelpContext`|El id. de contexto apropiado del archivo de Ayuda de Visual Basic para el error correspondiente a la propiedad `Number`.|  
|`LastDLLError`|Cero|  
  
 Si no existe un controlador de errores, o si no hay ninguno habilitado, se crea y se muestra un mensaje de error a partir de las propiedades del objeto `Err`.  
  
> [!NOTE]
>  Algunas aplicaciones host de Visual Basic no pueden crear objetos.  Consulte la documentación de la aplicación host para determinar si puede crear clases y objetos.  
  
## Ejemplo  
 En este ejemplo se utiliza la instrucción `Error` para generar el error número 11.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## Requisitos  
 **Espacio de nombres:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Ensamblado:** biblioteca en tiempo de ejecución de Visual Basic \(en Microsoft.VisualBasic.dll\)  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>   
 <xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>   
 [On Error \(Instrucción\)](../../../visual-basic/language-reference/statements/on-error-statement.md)   
 [Resume \(Instrucción\)](../../../visual-basic/language-reference/statements/resume-statement.md)   
 [Mensajes de error](../../../visual-basic/language-reference/error-messages/index.md)