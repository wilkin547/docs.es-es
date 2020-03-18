---
title: Procedimiento para buscar el nombre completo de un ensamblado
ms.date: 08/20/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 009dae23-e1f6-4a64-9a9a-32e4c34802b0
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 49ebaeabee7a346fb84f09e5a9e34590d1ea9811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348196"
---
# <a name="how-to-find-an-assemblys-fully-qualified-name"></a><span data-ttu-id="04be6-102">Procedimiento para buscar el nombre completo de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="04be6-102">How to: Find an assembly's fully qualified name</span></span>

<span data-ttu-id="04be6-103">Para conocer el nombre completo de un ensamblado de .NET Framework en la caché global de ensamblados, use la herramienta de esa caché ([Gacutil.exe](../../framework/tools/gacutil-exe-gac-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="04be6-103">To discover the fully qualified name of a .NET Framework assembly in the global assembly cache, use the Global Assembly Cache tool ([Gacutil.exe](../../framework/tools/gacutil-exe-gac-tool.md)).</span></span> <span data-ttu-id="04be6-104">Vea [Cómo: Consultar el contenido de la caché global de ensamblados](../../framework/app-domains/how-to-view-the-contents-of-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="04be6-104">See [How to: View the contents of the global assembly cache](../../framework/app-domains/how-to-view-the-contents-of-the-gac.md).</span></span>

<span data-ttu-id="04be6-105">En el caso de los ensamblados de .NET Core, y para los ensamblados de .NET Framework que no están en la caché global de ensamblados, puede obtener el nombre completo del ensamblado de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="04be6-105">For .NET Core assemblies, and for .NET Framework assemblies that aren't in the global assembly cache, you can get the fully qualified assembly name in a number of ways:</span></span>

- <span data-ttu-id="04be6-106">Puede usar código para mostrar esta información en la consola o en una variable; o bien puede usar [Ildasm.exe (el desensamblador de IL)](../../framework/tools/ildasm-exe-il-disassembler.md) para examinar los metadatos del ensamblado, los cuales contienen el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="04be6-106">You can use code to output the information to the console or to a variable, or you can use the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>

- <span data-ttu-id="04be6-107">Si el ensamblado ya está cargado por la aplicación, puede recuperar el valor de la propiedad <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> para obtener el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="04be6-107">If the assembly is already loaded by the application, you can retrieve the value of the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property to get the fully qualified name.</span></span> <span data-ttu-id="04be6-108">Puede usar la propiedad <xref:System.Type.Assembly> de un <xref:System.Type> definido en ese ensamblado para recuperar una referencia al objeto <xref:System.Reflection.Assembly>.</span><span class="sxs-lookup"><span data-stu-id="04be6-108">You can use the <xref:System.Type.Assembly> property of a <xref:System.Type> defined in that assembly to retrieve a reference to the <xref:System.Reflection.Assembly> object.</span></span> <span data-ttu-id="04be6-109">En este ejemplo se ilustra.</span><span class="sxs-lookup"><span data-stu-id="04be6-109">The example provides an illustration.</span></span>

- <span data-ttu-id="04be6-110">Si conoce la ruta de acceso al sistema de archivos del ensamblado, puede llamar al método `static` (C#) o `Shared` (Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> para obtener el nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="04be6-110">If you know the assembly's file system path, you can call the `static` (C#) or `Shared` (Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> method to get the fully qualified assembly name.</span></span> <span data-ttu-id="04be6-111">Este es un ejemplo sencillo.</span><span class="sxs-lookup"><span data-stu-id="04be6-111">The following is a simple example.</span></span>

  ```csharp
  using System;
  using System.Reflection;

  public class Example
  {
     public static void Main()
     {
        Console.WriteLine(AssemblyName.GetAssemblyName(@".\UtilityLibrary.dll"));
     }
  }
  // The example displays output like the following:
  //   UtilityLibrary, Version=1.1.0.0, Culture=neutral, PublicKeyToken=null
  ```

  ```vb
  Imports System.Reflection

  Public Module Example
     Public Sub Main
        Console.WriteLine(AssemblyName.GetAssemblyName(".\UtilityLibrary.dll"))
     End Sub
  End Module
  ' The example displays output like the following:
  '   UtilityLibrary, Version=1.1.0.0, Culture=neutral, PublicKeyToken=null
  ```

- <span data-ttu-id="04be6-112">Puede usar [Ildasm.exe (Desensamblador de MSIL)](../../framework/tools/ildasm-exe-il-disassembler.md) para examinar los metadatos del ensamblado, que contiene el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="04be6-112">You can use the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>

<span data-ttu-id="04be6-113">Para más información sobre el establecimiento de atributos del ensamblado como la versión, la referencia cultural y el nombre de ensamblado, vea [Establecimiento de atributos de ensamblado](set-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="04be6-113">For more information about setting assembly attributes such as version, culture, and assembly name, see [Set assembly attributes](set-attributes.md).</span></span> <span data-ttu-id="04be6-114">Para más información sobre cómo poner un nombre seguro a un ensamblado, vea [Creación y uso de ensamblados con nombre seguro](create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="04be6-114">For more information about giving an assembly a strong name, see [Create and use strong-named assemblies](create-use-strong-named.md).</span></span>

## <a name="example"></a><span data-ttu-id="04be6-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04be6-115">Example</span></span>

<span data-ttu-id="04be6-116">En el siguiente ejemplo se indica cómo mostrar el nombre completo de un ensamblado que contiene una clase especificada en la consola.</span><span class="sxs-lookup"><span data-stu-id="04be6-116">The following example shows how to display the fully qualified name of an assembly containing a specified class to the console.</span></span> <span data-ttu-id="04be6-117">Utiliza la propiedad <xref:System.Type.Assembly?displayProperty=nameWithType> para recuperar una referencia a un ensamblado de un tipo que se define en ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="04be6-117">It uses the <xref:System.Type.Assembly?displayProperty=nameWithType> property to retrieve a reference to an assembly from a type that's defined in that assembly.</span></span>

```cpp
#using <System.dll>
#using <System.Data.dll>

using namespace System;
using namespace System::Reflection;

ref class asmname
{
public:
    static void Main()
    {
        Type^ t = System::Data::DataSet::typeid;
        String^ s = t->Assembly->FullName->ToString();
        Console::WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s);
    }
};

int main()
{
    asmname::Main();
}
```

```csharp
using System;
using System.Reflection;

class asmname
{
    public static void Main()
    {
        Type t = typeof(System.Data.DataSet);
        string s = t.Assembly.FullName.ToString();
        Console.WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s);
    }
}
```

```vb
Imports System.Reflection

Class asmname
    Public Shared Sub Main()
        Dim t As Type = GetType(System.Data.DataSet)
        Dim s As String = t.Assembly.FullName.ToString()
        Console.WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s)
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="04be6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="04be6-118">See also</span></span>

- [<span data-ttu-id="04be6-119">Nombres de ensamblado</span><span class="sxs-lookup"><span data-stu-id="04be6-119">Assembly names</span></span>](names.md)
- [<span data-ttu-id="04be6-120">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="04be6-120">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="04be6-121">Creación y uso de ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="04be6-121">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="04be6-122">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="04be6-122">Global assembly cache</span></span>](../../framework/app-domains/gac.md)
- [<span data-ttu-id="04be6-123">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="04be6-123">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
