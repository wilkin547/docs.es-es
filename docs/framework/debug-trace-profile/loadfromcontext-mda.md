---
title: "loadFromContext MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), LoadFrom context"
  - "managed debugging assistants (MDAs), LoadFrom context"
  - "LoadFrom context"
  - "LoadFromContext MDA"
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# loadFromContext MDA
El asistente para la depuración administrada \(MDA\) de `loadFromContext` se activa si se carga un ensamblado en el contexto `LoadFrom`.  Esta situación puede producirse como consecuencia de llamar a <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> o a otros métodos similares.  
  
## Síntomas  
 El uso de algunos métodos de cargador puede dar lugar a que se carguen ensamblados en el contexto `LoadFrom`.  El uso de este contexto puede tener como consecuencia un comportamiento inesperado para la serialización, conversión y resolución de dependencia.  En general, se recomienda que los ensamblados se carguen en el contexto `Load` para evitar estos problemas.  Es difícil determinar en qué contexto se ha cargado un ensamblado sin este MDA.  
  
## Motivo  
 Por lo general, se ha cargado un ensamblado en el contexto `LoadFrom` si se cargó desde una ruta de acceso fuera del contexto `Load`, como la caché global de ensamblados o la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=fullName>.  
  
## Resolución  
 Configure las aplicaciones de manera que ya no se necesiten llamadas <xref:System.Reflection.Assembly.LoadFrom%2A>.  Puede utilizar las técnicas siguientes para realizar esa operación:  
  
-   Instale los ensamblados en la caché global de ensamblados.  
  
-   Coloque los ensamblados en el directorio <xref:System.AppDomainSetup.ApplicationBase%2A> para <xref:System.AppDomain>.  En el caso del dominio predeterminado, el directorio <xref:System.AppDomainSetup.ApplicationBase%2A> es el que contiene el archivo ejecutable que inició el proceso.  Esto también podría requerir la creación de un nuevo <xref:System.AppDomain> si no resulta práctico mover el ensamblado.  
  
-   Agregue una ruta de búsqueda al archivo de configuración de la aplicación \(.config\) o a dominios de aplicación secundarios si los ensamblados dependientes se encuentran en directorios secundarios con respecto al archivo ejecutable.  
  
 En cada caso, el código se puede cambiar para utilizar el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>.  
  
## Efecto en el Runtime  
 El MDA no tiene ningún efecto en el CLR.  Informa del contexto que se utilizó como resultado de una solicitud de carga.  
  
## Resultados  
 El MDA informa de que el ensamblado se cargó en el contexto `LoadFrom`.  Especifica el nombre sencillo del ensamblado y la ruta de acceso.  También sugiere mitigaciones para evitar el uso del contexto `LoadFrom`.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra una situación en la que se puede activar este MDA:  
  
```  
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is   
            // located outside of the Load context probing path.   
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## Vea también  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)