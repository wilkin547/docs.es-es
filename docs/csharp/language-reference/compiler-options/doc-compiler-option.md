---
title: -doc (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- FileProperties.BuildAction
- /doc
helpviewer_keywords:
- comments, C# code
- XML documentation [C#], comments in source files
- doc compiler option [C#]
- Visual C#, XML documentation for
- -doc compiler option [C#]
- /doc compiler option [C#]
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
ms.openlocfilehash: 01ea71f3de9e30abe25184e38a59f3707b54bd5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73422971"
---
# <a name="-doc-c-compiler-options"></a>-doc (Opciones del compilador de C#)
La opción **-doc** permite insertar comentarios de documentación en un archivo XML.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-doc:file  
```  
  
## <a name="arguments"></a>Argumentos  
 `file`  
 Archivo de salida para XML, que se llena con los comentarios de los archivos de código fuente de la compilación.  
  
## <a name="remarks"></a>Comentarios  
 En los archivos de código fuente, es posible procesar y agregar al archivo XML los comentarios de documentación que preceden a lo siguiente:  
  
- Tipos definidos por el usuario como una [clase](../keywords/class.md), un [delegado](../builtin-types/reference-types.md#the-delegate-type) o una [interfaz](../keywords/interface.md)  
  
- Miembros como un campo, un [evento](../keywords/event.md), una [propiedad](../../programming-guide/classes-and-structs/using-properties.md) o un método  
  
 El archivo de código fuente que contiene Main es la primera salida del XML.  
  
 Para usar el archivo .xml generado con la función [IntelliSense](/visualstudio/ide/using-intellisense), deje que el nombre del archivo .xml sea igual que el del ensamblado que quiere admitir y, después, asegúrese de que el archivo .xml se encuentra en el mismo directorio que el ensamblado. De este modo, cuando se hace referencia al ensamblado en el proyecto de Visual Studio, también se encuentra el archivo .xml. Vea [Proporcionar comentarios del código](/visualstudio/ide/reference/generate-xml-documentation-comments) para obtener más información.  
  
 A menos que compile con [-target:module](./target-module-compiler-option.md), `file` contendrá etiquetas \<assembly>\</assembly> que especifican el nombre del archivo que contiene el manifiesto del ensamblado para el archivo de salida de la compilación.  
  
> [!NOTE]
> La opción -doc se aplica a todos los archivos de entrada o, si se establece en la configuración del proyecto, a todos los archivos del proyecto. Para deshabilitar las advertencias relacionadas con los comentarios de documentación para un archivo específico o una sección de código, use [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).  
  
 Vea [Etiquetas recomendadas para comentarios de documentación ](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) para conocer las maneras de generar documentación a partir de comentarios en el código.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto.  
  
2. Haga clic en la pestaña **Compilar**.  
  
3. Modifique la propiedad **Archivo de documentación XML**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de proyectos y de soluciones](/visualstudio/ide/managing-project-and-solution-properties)
