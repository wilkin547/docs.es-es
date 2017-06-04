---
title: "memberInfoCacheCreation MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "member info cache creation"
  - "MemberInfoCacheCreation MDA"
  - "reflection, run-time errors"
  - "MDAs (managed debugging assistants), cache"
  - "cache [.NET Framework], reflection"
  - "managed debugging assistants (MDAs), cache"
  - "MemberInfo cache"
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# memberInfoCacheCreation MDA
El asistente para la depuración administrada \(MDA\) `memberInfoCacheCreation` se activa cuando se crea una caché <xref:System.Reflection.MemberInfo>.  Ésta es una indicación clara de que un programa está utilizando características de reflexión que consumen muchos recursos.  
  
## Síntomas  
 El espacio de trabajo de un programa aumenta porque el programa está utilizando una reflexión que consume muchos recursos.  
  
## Motivo  
 Las operaciones de reflexión en las que toman parte objetos <xref:System.Reflection.MemberInfo> se consideran como grandes consumidoras de recursos porque deben leer metadatos almacenados en páginas frías y en general indican que el programa está utilizando algún tipo de escenario enlazado en tiempo de ejecución.  
  
## Resolución  
 Puede determinar dónde se está utilizando la reflexión en su programa habilitando este MDA y ejecutando después el código en un depurador o adjuntándolo con un depurador cuando el MDA está activado.  Con un depurador obtendrá un seguimiento de pila que muestra dónde se creó la caché <xref:System.Reflection.MemberInfo> y, a partir de ahí, averiguar dónde está utilizando la reflexión su programa.  
  
 La resolución depende de los objetivos del código.  Este MDA le avisa de que su programa tiene un escenario enlazado en tiempo de ejecución.  Podría desear determinar si puede sustituir un escenario enlazado en tiempo de compilación o considerar el rendimiento del escenario enlazado en tiempo de ejecución.  
  
## Efecto en el Runtime  
 Este MDA se activa para cada caché <xref:System.Reflection.MemberInfo> creada.  El impacto en el rendimiento es inapreciable.  
  
## Resultados  
 El MDA genera un mensaje que indica que se creó la caché <xref:System.Reflection.MemberInfo>.  Utilice un depurador para obtener un seguimiento de la pila que muestra dónde está utilizando la reflexión su programa.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## Ejemplo  
 Este código de ejemplo activará el MDA `memberInfoCacheCreation`.  
  
```  
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## Vea también  
 <xref:System.Reflection.MemberInfo>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)