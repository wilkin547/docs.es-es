---
title: "Cómo: Determinar si un archivo es un ensamblado (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 09e56f3c0310a519594d0a53d8094275e1accec6
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a>Cómo: Determinar si un archivo es un ensamblado (C#)
Un archivo es un ensamblado únicamente si está administrado y contiene una entrada de ensamblado en sus metadatos. Para más información sobre ensamblados y metadatos, vea el tema [Manifiesto del ensamblado](../../../../../docs/framework/app-domains/assembly-manifest.md).  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>Cómo determinar manualmente si un archivo es un ensamblado  
  
1.  Inicie [Ildasm.exe (el desensamblador de lenguaje intermedio)](https://msdn.microsoft.com/library/f7dy01k1).  
  
2.  Cargue el archivo que quiere probar.  
  
3.  Si **ILDASM** notifica que el archivo no es un archivo ejecutable portable (PE), entonces no es un ensamblado. Para obtener más información, vea el tema [Cómo: Ver el contenido de un ensamblado](../../../../framework/app-domains/how-to-view-assembly-contents.md).  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>Cómo determinar mediante programación si un archivo es un ensamblado  
  
1.  Llame al método <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>; para ello, pase el nombre y la ruta de acceso de archivo completa del archivo que está probando.  
  
2.  Si se genera una excepción <xref:System.BadImageFormatException>, el archivo no es un ensamblado.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se prueba un archivo DLL para ver si es un ensamblado.  
  
```  
class TestAssembly  
{  
    static void Main()  
    {  
  
        try  
        {  
            System.Reflection.AssemblyName testAssembly =  
                System.Reflection.AssemblyName.GetAssemblyName(@"C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll");  
  
            System.Console.WriteLine("Yes, the file is an assembly.");  
        }  
  
        catch (System.IO.FileNotFoundException)  
        {  
            System.Console.WriteLine("The file cannot be found.");  
        }  
  
        catch (System.BadImageFormatException)  
        {  
            System.Console.WriteLine("The file is not an assembly.");  
        }  
  
        catch (System.IO.FileLoadException)  
        {  
            System.Console.WriteLine("The assembly has already been loaded.");  
        }  
    }  
}  
/* Output (with .NET Framework 3.5 installed):  
    Yes, the file is an assembly.  
*/  
```  
  
 El método <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> carga el archivo de prueba y, después, lo libera cuando se lee la información.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Reflection.AssemblyName>  
 [Guía de programación de C#](../../../../csharp/programming-guide/index.md)  
 [Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) (Ensamblados y caché global de ensamblados [C#])
