---
title: "#line (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#line"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#line (directiva) [C#]"
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #line (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`#line` permite modificar el número de línea del compilador y \(opcionalmente\) el nombre del archivo que aparece en los resultados de errores y advertencias del compilador.  El ejemplo siguiente muestra cómo notificar dos advertencias asociadas a números de líneas.  La directiva `#line 200` hace que el número de línea sea 200 \(si bien el valor predeterminado es \#7\) y, hasta la siguiente directiva \#line, el nombre de archivo será "Special".  La directiva \#line default restablece la numeración de las líneas en la numeración predeterminada, que realiza un recuento de las líneas cuya numeración cambió por la directiva anterior.  
  
```  
class MainClass  
{  
    static void Main()  
    {  
#line 200 "Special"  
        int i;    // CS0168 on line 200  
        int j;    // CS0168 on line 201  
#line default  
        char c;   // CS0168 on line 9  
        float f;  // CS0168 on line 10  
#line hidden // numbering not affected  
        string s;   
        double d; // CS0168 on line 13  
    }  
}  
```  
  
## Comentarios  
 La directiva `#line` podría utilizarse en un paso intermedio automatizado del proceso de compilación.  Por ejemplo, si se quitaron las líneas del archivo de código fuente original, pero aún se desea que el compilador genere unos resultados basados en la numeración de líneas original del archivo, se pueden quitar las líneas y, a continuación, simular la numeración original mediante `#line`.  
  
 La directiva `#line hidden` oculta las sucesivas líneas del depurador, de manera que cuando el desarrollador avanza por el código, evita cualquier línea que haya entre una directiva `#line hidden` y la siguiente directiva `#line` \(suponiendo que no haya otra directiva `#line hidden`\).  Esta opción también puede utilizarse para permitir a ASP.NET que diferencie entre el código definido por el usuario y el generado por el equipo.  Aunque ASP.NET es el primer usuario de esta característica, es probable que más generadores de código fuente hagan uso de ella.  
  
 Una directiva `#line hidden` no afecta ni a los nombres de los archivos ni a los números de líneas en la generación de informes de error.  Es decir, si se encuentra un error en un bloque oculto, el compilador informará del nombre del archivo en uso y del número de la línea en que se encuentra el error.  
  
 La directiva `#line filename` especifica el nombre del archivo que debe aparecer en los resultados del compilador.  El nombre predeterminado es el nombre real del archivo de código fuente.  El nombre de archivo debe estar entre comillas \(""\) y debe ir precedido por un número de línea.  
  
 Un archivo de código fuente puede tener cualquier número de directivas `#line`.  
  
## Ejemplo 1  
 En el ejemplo siguiente se muestra cómo el depurador omite las líneas ocultas en el código.  Cuando ejecute el ejemplo, mostrará tres líneas de texto.  Sin embargo, cuando establezca un punto de interrupción, como se muestra en el ejemplo, y presione F10 para avanzar por el código, observará que el depurador omite la línea oculta.  Observe también que incluso si establece un punto de interrupción en la línea oculta, el depurador seguirá omitiéndola.  
  
```  
// preprocessor_linehidden.cs  
using System;  
class MainClass   
{  
    static void Main()   
    {  
        Console.WriteLine("Normal line #1."); // Set break point here.  
#line hidden  
        Console.WriteLine("Hidden line.");  
#line default  
        Console.WriteLine("Normal line #2.");  
    }  
}  
```  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Directivas de preprocesador de C\#](../../../csharp/language-reference/preprocessor-directives/index.md)