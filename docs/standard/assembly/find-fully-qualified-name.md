---
title: Procedimiento para buscar el nombre completo de un ensamblado
description: En este artículo se muestra cómo obtener el nombre completo de un ensamblado de .NET Framework o de .NET Core.
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
ms.openlocfilehash: 346d50dc7f279ce46c9803ad60479d3111739c25
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378943"
---
# <a name="how-to-find-an-assemblys-fully-qualified-name"></a>Procedimiento para buscar el nombre completo de un ensamblado

Para conocer el nombre completo de un ensamblado de .NET Framework en la caché global de ensamblados, use la herramienta de esa caché ([Gacutil.exe](../../framework/tools/gacutil-exe-gac-tool.md)). Vea [Cómo: Consultar el contenido de la caché global de ensamblados](../../framework/app-domains/how-to-view-the-contents-of-the-gac.md).

En el caso de los ensamblados de .NET Core, y para los ensamblados de .NET Framework que no están en la caché global de ensamblados, puede obtener el nombre completo del ensamblado de varias maneras:

- Puede usar código para mostrar esta información en la consola o en una variable; o bien puede usar [Ildasm.exe (el desensamblador de IL)](../../framework/tools/ildasm-exe-il-disassembler.md) para examinar los metadatos del ensamblado, los cuales contienen el nombre completo.

- Si el ensamblado ya está cargado por la aplicación, puede recuperar el valor de la propiedad <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> para obtener el nombre completo. Puede usar la propiedad <xref:System.Type.Assembly> de un <xref:System.Type> definido en ese ensamblado para recuperar una referencia al objeto <xref:System.Reflection.Assembly>. En este ejemplo se ilustra.

- Si conoce la ruta de acceso al sistema de archivos del ensamblado, puede llamar al método `static` (C#) o `Shared` (Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> para obtener el nombre completo del ensamblado. Este es un ejemplo sencillo.

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

- Puede usar [Ildasm.exe (Desensamblador de MSIL)](../../framework/tools/ildasm-exe-il-disassembler.md) para examinar los metadatos del ensamblado, que contiene el nombre completo.

Para más información sobre el establecimiento de atributos del ensamblado como la versión, la referencia cultural y el nombre de ensamblado, vea [Establecimiento de atributos de ensamblado](set-attributes.md). Para más información sobre cómo poner un nombre seguro a un ensamblado, vea [Creación y uso de ensamblados con nombre seguro](create-use-strong-named.md).

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se indica cómo mostrar el nombre completo de un ensamblado que contiene una clase especificada en la consola. Utiliza la propiedad <xref:System.Type.Assembly?displayProperty=nameWithType> para recuperar una referencia a un ensamblado de un tipo que se define en ese ensamblado.

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

## <a name="see-also"></a>Vea también

- [Nombres de ensamblado](names.md)
- [Creación de ensamblados](create.md)
- [Creación y uso de ensamblados con nombre seguro](create-use-strong-named.md)
- [Caché global de ensamblados](../../framework/app-domains/gac.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../framework/deployment/how-the-runtime-locates-assemblies.md)
