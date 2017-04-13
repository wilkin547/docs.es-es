---
title: "bindingFailure MDA | Microsoft Docs"
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
  - "binding failure"
  - "binding, failures"
  - "MDAs (managed debugging assistants), binding failures"
  - "assemblies [.NET Framework], binding failures"
  - "managed debugging assistants (MDAs), binding failures"
  - "BindingFailure MDA"
ms.assetid: 26ada5af-175c-4576-931a-9f07fa1723e9
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# bindingFailure MDA
El asistente para la depuración administrada \(MDA\) de `bindingFailure` se activa cuando se produce un error al cargar un ensamblado.  
  
## Síntomas  
 El código ha intentado cargar un ensamblado utilizando una referencia estática o uno de los métodos del cargador, como <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>.  El ensamblado no se ha cargado y se ha producido una excepción <xref:System.IO.FileNotFoundException> o <xref:System.IO.FileLoadException>.  
  
## Motivo  
 Cuando el motor en tiempo de ejecución no es capaz de cargar un ensamblado, se produce un error de enlace.  Un error de enlace puede producirse como resultado de una de las situaciones siguientes:  
  
-   Common Language Runtime \(CLR\) no puede encontrar el ensamblado solicitado.  Hay muchas razones por las que esto puede ocurrir; por ejemplo, que el ensamblado no se haya instalado o que la aplicación no se haya configurado correctamente para que busque el ensamblado.  
  
-   El hecho pasar un tipo a otro dominio de aplicación constituye un escenario común de problemas, ya que es necesario que CLR cargue el ensamblado que contiene el tipo en el segundo dominio de aplicación.  Es posible que el motor en tiempo de ejecución no pueda cargar el ensamblado si el segundo dominio de aplicación está configurado de forma distinta al dominio de aplicación original.  Por ejemplo, los dos dominios de aplicación podrían tener valores de propiedad distintos para <xref:System.AppDomain.BaseDirectory%2A>.  
  
-   El ensamblado solicitado está dañado o no es un ensamblado.  
  
-   El código que está intentando cargar el ensamblado no dispone de permisos adecuados de seguridad de acceso del código para cargar ensamblados.  
  
-   Las credenciales de usuario no proporcionan los permisos necesarios para leer el archivo.  
  
## Resolución  
 El primer paso consiste en determinar por qué el CLR no ha podido enlazarse al ensamblado solicitado.  Hay muchas razones por las que el motor en tiempo de ejecución puede no haber encontrado o no haber sido capaz de cargar el ensamblado solicitado como, por ejemplo, los escenarios que se muestran en la sección Motivo.  Es recomendable llevar a cabo las siguientes acciones para eliminar la causa del error de enlace:  
  
-   Determine la causa utilizando los datos proporcionados por el MDA de `bindingFailure`:  
  
    -   Ejecute [Fuslogvw.exe \(Assembly Binding Log Viewer\)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md) para leer los registros de errores generados por el enlazador del ensamblado.  
  
    -   Determine si el ensamblado se encuentra en la ubicación solicitada.  En el caso de los métodos <xref:System.Reflection.Assembly.LoadFrom%2A> y <xref:System.Reflection.Assembly.LoadFile%2A>, la ubicación solicitada puede determinarse con facilidad.  En el caso del método <xref:System.Reflection.Assembly.Load%2A>, que se sirve de la identidad del ensamblado para realizar el enlace, deberá buscar ensamblados que coincidan con esa identidad en la ruta de búsqueda de la propiedad <xref:System.AppDomain.BaseDirectory%2A> del dominio de aplicación y en la caché global de ensamblados.  
  
-   Averigüe la causa basándose en la determinación anterior.  Entre las posibles opciones de solución se encuentran las siguientes:  
  
    -   Instale el ensamblado solicitado en la memoria caché global de ensamblados y llame al método  <xref:System.Reflection.Assembly.Load%2A> para cargar el ensamblado por su identidad.  
  
    -   Copie el ensamblado solicitado en el directorio de la aplicación y llame al método <xref:System.Reflection.Assembly.Load%2A> para cargar el ensamblado por su identidad.  
  
    -   Vuelva a configurar el dominio de aplicación en que se produjo el error de enlace para que incluya la ruta del ensamblado; para ello, modifique la propiedad <xref:System.AppDomain.BaseDirectory%2A> o agregue rutas de búsqueda privadas.  
  
    -   Cambie la lista de control de acceso del archivo para que el usuario que ha iniciado la sesión actual pueda leer el archivo.  
  
## Efecto en el Runtime  
 Este MDA no tiene efecto en el CLR.  Sólo informa de los datos relacionados con los errores de enlace.  
  
## Resultados  
 El MDA registra el ensamblado que ha producido un error al cargarse, e incluye la ruta de acceso solicitada o el nombre para mostrar, el contexto de enlace, el dominio de aplicación donde se ha solicitado la carga y el motivo del error.  
  
 El nombre para mostrar o la ruta de acceso solicitada pueden estar en blanco si estos datos no estaban disponibles para CLR.  Si la llamada que ha producido el error corresponde al método <xref:System.Reflection.Assembly.Load%2A>, es probable que el motor en tiempo de ejecución no pueda determinar el nombre para mostrar del ensamblado.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <bindingFailure />  
  </assistants>  
</mdaConfig>  
```  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra una situación en la que se puede activar este MDA:  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // This call attempts to load a nonexistent assembly.  
            // The call will throw a System.IO.FileNotFound exception  
            // and cause the activation of the bindingFailure MDA   
            // if it is registered.  
            Assembly.Load("NonExistentAssembly");  
        }  
    }  
}  
```  
  
## Vea también  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)