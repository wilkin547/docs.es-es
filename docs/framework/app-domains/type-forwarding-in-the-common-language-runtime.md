---
title: "Reenv&#237;o de tipos en Common Language Runtime | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ensamblados [.NET Framework], reenvío de tipos"
  - "reenvío de tipos"
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Reenv&#237;o de tipos en Common Language Runtime
El reenvío de tipos le permite mover un tipo a otro ensamblado sin tener que volver a compilar las aplicaciones que utilizan el ensamblado original.  
  
 Por ejemplo, supongamos que una aplicación utiliza la clase `Example` en un ensamblado denominado `Utility.dll`.  Los desarrolladores de `Utility.dll` podrían decidir refactorizar el ensamblado y, en el proceso, podrían mover la clase `Example` a otro ensamblado.  Si se reemplaza la versión antigua de `Utility.dll` por la nueva versión de `Utility.dll` y su ensamblado complementario, se producirá un error en la aplicación que utiliza la clase `Example` porque no podrá localizar la clase `Example` en la nueva versión de `Utility.dll`.  
  
 Los desarrolladores de `Utility.dll` pueden evitarlo reenviando solicitudes a la clase `Example` mediante el atributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>.  Si el atributo ya se ha aplicado a la nueva versión de `Utility.dll`, las solicitudes a la clase `Example` se reenviarán al ensamblado que en estos momentos contenga la clase.  La aplicación existente continuará funcionando normalmente, sin volver a compilarse.  
  
> [!NOTE]
>  En la versión 2.0 de .NET Framework, no pueden reenviarse tipos de ensamblados escritos en Visual Basic.  Pero una aplicación escrita en Visual Basic puede utilizar tipos reenviados.  Es decir, si la aplicación utiliza un ensamblado codificado en C\# o C\+\+ y un tipo de ese ensamblado se reenvía a otro ensamblado, la aplicación de Visual Basic puede utilizar el tipo reenviado.  
  
## Reenviar tipos  
 Para reenviar un tipo, hay que seguir cuatro pasos:  
  
1.  Mueva el código fuente del tipo del ensamblado original al ensamblado de destino.  
  
2.  En el ensamblado donde antes estaba localizado el tipo, agregue <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> al tipo que se ha movido.  En el siguiente código se muestra el atributo para un tipo denominado `Example` que se ha movido.  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp#  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3.  Compile el ensamblado que en estos momentos contenga el tipo.  
  
4.  Vuelva a compilar el ensamblado donde antes estaba localizado el tipo, con una referencia al ensamblado que en estos momentos contenga el tipo.  Por ejemplo, si está compilando un archivo de C\# desde la línea de comandos, utilice la opción [\/reference \(Import Metadata\)](../Topic/-reference%20\(C%23%20Compiler%20Options\).md) para especificar el ensamblado que contiene el tipo.  En C\+\+, utilice la directiva [\#using](../Topic/%23using%20Directive%20\(C++\).md) del archivo de código fuente para especificar el ensamblado que contiene el tipo.  
  
## Vea también  
 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>   
 [Reenvío de tipos \(C\+\+\/CLI\)](../Topic/Type%20Forwarding%20\(C++-CLI\).md)   
 [\#using \(Directiva\)](../Topic/%23using%20Directive%20\(C++\).md)