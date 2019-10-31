---
title: 'Cómo: Agregar referencias a bibliotecas de tipos'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
ms.openlocfilehash: b4b78d377cf3ff2b43f7776567583c71c479054c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123956"
---
# <a name="how-to-add-references-to-type-libraries"></a>Cómo: Agregar referencias a bibliotecas de tipos
Visual Studio genera un ensamblado de interoperabilidad que contiene metadatos cuando se agrega una referencia a una biblioteca de tipos. Si el ensamblado de interoperabilidad principal está disponible, Visual Studio usa el ensamblado existente antes de generar un nuevo ensamblado de interoperabilidad.  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a>Para agregar una referencia a una biblioteca de tipos en Visual Studio  
  
1. Instale el archivo COM DLL o EXE en su equipo, a menos que un archivo Setup.exe de Windows realice la instalación automáticamente.  
  
2. Seleccione **Proyecto**, **Agregar referencia**.  
  
3. En el Administrador de referencias, elija **COM**.  
  
4. Seleccione la biblioteca de tipos en la lista o busque el archivo .tlb.  
  
5. Elija **Aceptar**.  
  
6. En el Explorador de soluciones, abra el menú contextual de la referencia que acaba de agregar y elija **Propiedades**.  
  
7. En la ventana **Propiedades**, asegúrese de que el valor de la propiedad **Incrustar tipos de interoperabilidad** es **True**. Esto hace que Visual Studio incruste información sobre los tipos COM en los ejecutables, eliminando así la necesidad de implementar ensamblados de interoperabilidad principales con la aplicación.  
  
> [!NOTE]
> Las opciones de los menús y cuadros de diálogo puede variar según la versión de Visual Studio que esté usando.  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a>Para agregar una referencia a una biblioteca de tipos para la compilación en la línea de comandos  
  
1. Genere un ensamblado de interoperabilidad, como se describe en [Cómo: Generar ensamblados de interoperabilidad a partir de bibliotecas de tipos](how-to-generate-interop-assemblies-from-type-libraries.md).  
  
2. Use la opción [-LinkC# (opciones del compilador)](../../csharp/language-reference/compiler-options/link-compiler-option.md) o [-Link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) del compilador con el nombre de ensamblado de interoperabilidad para insertar información de tipos para los tipos com en los ejecutables.  
  
## <a name="see-also"></a>Vea también

- [Importar una biblioteca de tipos como un ensamblado](importing-a-type-library-as-an-assembly.md)
- [Exponer componentes COM en .NET Framework](exposing-com-components.md)
- [Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio](../../standard/assembly/embed-types-visual-studio.md) 
- [-link (Opciones del compilador de C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md)
