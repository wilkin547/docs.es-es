---
title: 'Cómo: Determinar si un archivo es un ensamblado (C#)'
ms.date: 07/20/2015
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
ms.openlocfilehash: ee2313677fba21624ccdb44db779633f6c4503bf
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861015"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a><span data-ttu-id="de7cc-102">Cómo: Determinar si un archivo es un ensamblado (C#)</span><span class="sxs-lookup"><span data-stu-id="de7cc-102">How to: Determine If a File Is an Assembly (C#)</span></span>
<span data-ttu-id="de7cc-103">Un archivo es un ensamblado únicamente si está administrado y contiene una entrada de ensamblado en sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="de7cc-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="de7cc-104">Para más información sobre ensamblados y metadatos, vea el tema [Manifiesto del ensamblado](../../../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="de7cc-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](../../../../../docs/framework/app-domains/assembly-manifest.md).</span></span>  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="de7cc-105">Cómo determinar manualmente si un archivo es un ensamblado</span><span class="sxs-lookup"><span data-stu-id="de7cc-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="de7cc-106">Inicie [Ildasm.exe (el desensamblador de lenguaje intermedio)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="de7cc-106">Start the [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2.  <span data-ttu-id="de7cc-107">Cargue el archivo que quiere probar.</span><span class="sxs-lookup"><span data-stu-id="de7cc-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="de7cc-108">Si **ILDASM** notifica que el archivo no es un archivo ejecutable portable (PE), entonces no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="de7cc-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="de7cc-109">Para obtener más información, vea el tema [Cómo: Ver el contenido de un ensamblado](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span><span class="sxs-lookup"><span data-stu-id="de7cc-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="de7cc-110">Cómo determinar mediante programación si un archivo es un ensamblado</span><span class="sxs-lookup"><span data-stu-id="de7cc-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="de7cc-111">Llame al método <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>; para ello, pase el nombre y la ruta de acceso de archivo completa del archivo que está probando.</span><span class="sxs-lookup"><span data-stu-id="de7cc-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="de7cc-112">Si se genera una excepción <xref:System.BadImageFormatException>, el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="de7cc-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de7cc-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="de7cc-113">Example</span></span>  
 <span data-ttu-id="de7cc-114">En este ejemplo se prueba un archivo DLL para ver si es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="de7cc-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
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
  
 <span data-ttu-id="de7cc-115">El método <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> carga el archivo de prueba y, después, lo libera cuando se lee la información.</span><span class="sxs-lookup"><span data-stu-id="de7cc-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de7cc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="de7cc-116">See Also</span></span>

- <xref:System.Reflection.AssemblyName>  
- [<span data-ttu-id="de7cc-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="de7cc-117">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
- <span data-ttu-id="de7cc-118">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) (Ensamblados y caché global de ensamblados [C#])</span><span class="sxs-lookup"><span data-stu-id="de7cc-118">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)</span></span>
