---
title: Resolución de cargas de ensamblado
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], resolving loads
- application domains, loading assemblies
- resolving assembly loads
- assemblies [.NET Framework], loading
- application domains, resolving assembly loads
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: d6314fae266505fbb4410aaaa351973070ab3811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78156444"
---
# <a name="resolve-assembly-loads"></a>Resolución de cargas de ensamblado
.NET proporciona el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> para aplicaciones que requieren un mayor control sobre la carga de ensamblados. Al controlar este evento, la aplicación puede cargar un ensamblado en el contexto de carga desde fuera de las rutas de acceso de sondeo normales, seleccionar qué versión de ensamblado cargar, emitir un ensamblado dinámico y devolverlo, etc. En este tema se proporcionan instrucciones para controlar el evento <xref:System.AppDomain.AssemblyResolve>.  
  
> [!NOTE]
> Para resolver cargas de ensamblado en el contexto de solo reflexión, use en su lugar el evento <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType>.  
  
## <a name="how-the-assemblyresolve-event-works"></a>Cómo funciona el evento AssemblyResolve  
 Al registrar un controlador para el evento <xref:System.AppDomain.AssemblyResolve>, se invoca el controlador si se produce un error cuando el tiempo de ejecución enlaza a un ensamblado por nombre. Por ejemplo, si se llama a los métodos siguientes desde el código de usuario, puede producirse el evento <xref:System.AppDomain.AssemblyResolve>:  
  
- Una sobrecarga del método <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> o una sobrecarga del método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> cuyo primer argumento es una cadena que representa el nombre para mostrar del ensamblado que se va a cargar (es decir, la cadena devuelta por la propiedad <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>).  
  
- Una sobrecarga del método <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> o una sobrecarga del método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> cuyo primer argumento es un objeto <xref:System.Reflection.AssemblyName> que identifica el ensamblado que se va a cargar.  
  
- Una sobrecarga del método <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.  
  
- Una sobrecarga del método <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> que crea instancias de un objeto en otro dominio de aplicación.  
  
### <a name="what-the-event-handler-does"></a>Qué hace el controlador de eventos  
 El controlador del evento <xref:System.AppDomain.AssemblyResolve> recibe el nombre para mostrar del ensamblado que se va a cargar, en la propiedad <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType>. Si el controlador no reconoce el nombre del ensamblado, devuelve `null` (C#), `Nothing` (Visual Basic) o `nullptr` (Visual C++).  
  
 Si el controlador reconoce el nombre del ensamblado, puede cargar y devolver un ensamblado que cumpla la solicitud. En la lista siguiente se describen algunos escenarios de ejemplo.  
  
- Si el controlador conoce la ubicación de una versión del ensamblado, puede cargar el ensamblado mediante el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> y devolver el ensamblado cargado si se realiza correctamente.  
  
- Si el controlador tiene acceso a una base de datos de los ensamblados almacenados como matrices de bytes, puede cargar una matriz de bytes mediante una de las sobrecargas del método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> que toman una matriz de bytes.  
  
- El controlador puede generar un ensamblado dinámico y devolverlo.  
  
> [!NOTE]
> El controlador debe cargar el ensamblado en el contexto de origen de carga, en el contexto de carga o sin contexto. Si el controlador carga el ensamblado en el contexto de solo reflexión mediante el método <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType>, se produce un error en el intento de carga que ha provocado el evento <xref:System.AppDomain.AssemblyResolve>.  
  
 El controlador de eventos se encarga de devolver un ensamblado adecuado. El controlador puede analizar el nombre para mostrar del ensamblado solicitado. Para ello, pasa el valor de propiedad <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> al constructor <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29>. A partir de .NET Framework 4, el controlador puede usar la propiedad <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> para determinar si la solicitud actual es una dependencia de otro ensamblado. Esta información puede ayudar a identificar un ensamblado que cumplirá la dependencia.  
  
 El controlador de eventos puede devolver una versión del ensamblado diferente de la versión solicitada.  
  
 En la mayoría de los casos, el ensamblado que el controlador devuelve aparece en el contexto de carga, independientemente del contexto en el que lo carga el controlador. Por ejemplo, si el controlador usa el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> para cargar un ensamblado en el contexto de origen de carga, el ensamblado aparece en el contexto de carga cuando el controlador lo devuelve. Pero en el caso siguiente, el ensamblado aparece sin contexto cuando el controlador lo devuelve:  
  
- El controlador carga un ensamblado sin contexto.  
  
- La propiedad <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> no es NULL.  
  
- El ensamblado solicitante (es decir, el ensamblado devuelto por la propiedad <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType>) se ha cargado sin contexto.  
  
 Para obtener información sobre los contextos, vea la sobrecarga del método <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType>.  
  
 Es posible cargar varias versiones del mismo ensamblado en el mismo dominio de aplicación, pero esta práctica no se recomienda porque puede provocar problemas de asignación de tipos. Vea [Procedimientos recomendados para cargar ensamblados](../../framework/deployment/best-practices-for-assembly-loading.md).  
  
### <a name="what-the-event-handler-should-not-do"></a>Qué no debe hacer el controlador de eventos  
La regla principal que debe observar para controlar el evento <xref:System.AppDomain.AssemblyResolve> es que no debe intentar devolver un ensamblado que no reconozca. Cuando se escribe el controlador, debe saber qué ensamblados pueden hacer que se produzca el evento. El controlador debe devolver NULL para otros ensamblados.  

> [!IMPORTANT]
> A partir de .NET Framework 4, se genera el evento <xref:System.AppDomain.AssemblyResolve> para los ensamblados satélite. Este cambio afecta a los controladores de eventos escritos para versiones anteriores de .NET Framework si intentan resolver todas las solicitudes de carga del ensamblado. Los controladores de eventos que omiten los ensamblados que no reconocen no se ven afectados por este cambio: devuelven NULL y se siguen los mecanismos normales de reserva.  

Al cargar un ensamblado, el controlador de eventos no debe usar las sobrecargas del método <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> que pueden hacer que se produzca el evento <xref:System.AppDomain.AssemblyResolve> de forma recursiva, ya que esto puede provocar un desbordamiento de pila. (Vea la lista proporcionada anteriormente en este tema). Esto ocurre incluso si proporciona el control de excepciones para la solicitud de carga, porque no se produce ninguna excepción hasta que se hayan devuelto todos los controladores de eventos. Así pues, el código siguiente produce un desbordamiento de pila si no se encuentra `MyAssembly`:  

```cpp
using namespace System;
using namespace System::Reflection;

ref class Example
{
internal:
    static Assembly^ MyHandler(Object^ source, ResolveEventArgs^ e)
    {
        Console::WriteLine("Resolving {0}", e->Name);
        return Assembly::Load(e->Name);
    }
};

void main()
{
    AppDomain^ ad = AppDomain::CreateDomain("Test");
    ad->AssemblyResolve += gcnew ResolveEventHandler(&Example::MyHandler);

    try
    {
        Object^ obj = ad->CreateInstanceAndUnwrap(
            "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
            "MyType");
    }
    catch (Exception^ ex)
    {
        Console::WriteLine(ex->Message);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```csharp
using System;
using System.Reflection;

class BadExample
{
    static void Main()
    {
        AppDomain ad = AppDomain.CreateDomain("Test");
        ad.AssemblyResolve += MyHandler;

        try
        {
            object obj = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType");
        }
        catch (Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
    }

    static Assembly MyHandler(object source, ResolveEventArgs e)
    {
        Console.WriteLine("Resolving {0}", e.Name);
        return Assembly.Load(e.Name);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```vb
Imports System.Reflection

Class BadExample

    Shared Sub Main()

        Dim ad As AppDomain = AppDomain.CreateDomain("Test")
        AddHandler ad.AssemblyResolve, AddressOf MyHandler

        Try
            Dim obj As object = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType")
        Catch ex As Exception
            Console.WriteLine(ex.Message)
        End Try
    End Sub

    Shared Function MyHandler(ByVal source As Object, _
                              ByVal e As ResolveEventArgs) As Assembly
        Console.WriteLine("Resolving {0}", e.Name)
        Return Assembly.Load(e.Name)
    End Function
End Class

' This example produces output similar to the following:
'
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'...
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'
'Process is terminated due to StackOverflowException.
```

## <a name="see-also"></a>Vea también

- [Procedimientos recomendados para cargar ensamblados](../../framework/deployment/best-practices-for-assembly-loading.md)
- [Utilizar dominios de aplicación](../../framework/app-domains/use.md)
