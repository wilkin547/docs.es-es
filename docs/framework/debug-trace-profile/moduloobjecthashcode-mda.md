---
title: "moduloObjectHashcode MDA | Microsoft Docs"
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
  - "managed debugging assistants (MDAs), hashcode modulus"
  - "Modulo object hash code"
  - "moduloObjectHashcode MDA"
  - "hashcode modulus"
  - "MDAs (managed debugging assistants), hashcode modulus"
  - "GetHashCode method"
  - "modulus of hashcodes"
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# moduloObjectHashcode MDA
El asistente para la depuración administrada \(MDA\) `moduloObjectHashcode` cambia el comportamiento de la clase <xref:System.Object> para que realice una operación de módulo en el código hash devuelto por el método <xref:System.Object.GetHashCode%2A>.  El módulo predeterminado para MDA es 1, que hace que <xref:System.Object.GetHashCode%2A> devuelva 0 para todos los objetos.  
  
## Síntomas  
 Después de actualizar a una nueva versión de Common Language Runtime \(CLR\), un programa deja de ejecutarse correctamente:  
  
-   El programa está recibiendo el objeto equivocado de una <xref:System.Collections.Hashtable>.  
  
-   El orden de enumeración de una <xref:System.Collections.Hashtable> tiene un cambio que interrumpe el programa.  
  
-   Dos objetos que eran iguales ya no son iguales.  
  
-   Dos objetos que no eran iguales ahora son iguales.  
  
## Motivo  
 Su programa puede estar recibiendo un objeto equivocado desde una <xref:System.Collections.Hashtable> porque la implementación del método <xref:System.Object.Equals%2A> en la clase para que la clave pasada a <xref:System.Collections.Hashtable> compruebe si son iguales los objetos comparando los resultados de la llamada al método <xref:System.Object.GetHashCode%2A>.  Los códigos hash no deberían utilizarse para comprobar si los objetos son iguales porque dos objetos pueden tener el mismo código hash incluso si sus respectivos campos tienen valores distintos.  Estas colisiones de código hash, aunque sean raras en la práctica, se producen.  El efecto que este fenómeno ejerce en una consulta de <xref:System.Collections.Hashtable> es que dos claves que no son iguales parecen serlo y se devuelve el objeto incorrecto desde la <xref:System.Collections.Hashtable>.  Por motivos de rendimiento, la implementación de <xref:System.Object.GetHashCode%2A> puede cambiar entre las versiones en tiempo de ejecución, por lo que las colisiones que podrían no producirse en una versión sí es posible que se produzcan en versiones posteriores.  Habilite este MDA para probar si en su código aparecen errores cuando se producen colisiones de códigos hash.  Cuando está habilitado, este MDA hace que el método <xref:System.Object.GetHashCode%2A> devuelva 0, lo que hace que todos los códigos hash entren en colisión.  El único efecto que debería tener la habilitación de este MDA en su programa es que éste se ejecuta más lentamente.  
  
 El orden de enumeración de una <xref:System.Collections.Hashtable> puede cambiar de una versión en tiempo de ejecución a otra si cambia el algoritmo utilizado para calcular los códigos hash de la clave.  Para comprobar si su programa ha tomado una dependencia en el orden de enumeración de las claves o valores de una tabla hash, puede habilitar este MDA.  
  
## Resolución  
 Nunca utilice los códigos hash como suplente para la identidad de los objetos.  Implemente el reemplazo del <xref:System.Object.Equals%2A?displayProperty=fullName> para que no se comparen los códigos hash.  
  
 No cree dependencias en el orden de enumeraciones de claves o valores en tablas hash.  
  
## Efecto en el Runtime  
 Las aplicaciones se ejecutan más despacio cuando este MDA está habilitado.  Este MDA simplemente toma el código hash que se habría devuelto y, en su lugar, devuelve el resto cuando se divide por un módulo.  
  
## Resultados  
 Este MDA no produce ningún resultado.  
  
## Configuration  
 El atributo `modulus` especifica el módulo utilizado en el código hash.  El valor predeterminado es 1.  
  
```  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)