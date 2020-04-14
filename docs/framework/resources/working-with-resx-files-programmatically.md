---
title: Trabajar con archivos .resx mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resource files, .resx files
- .resx files
ms.assetid: 168f941a-2b84-43f8-933f-cf4a8548d824
ms.openlocfilehash: 3b84d77e4ac9b9889d1bc2f08e5ead6b81deecb0
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243042"
---
# <a name="work-with-resx-files-programmatically"></a>Trabajar con archivos .resx mediante programación

Como los archivos de recursos (.resx) XML deben constar de código XML bien definido e incluir un encabezado según un esquema concreto, seguido de datos en pares nombre/valor, es posible que la creación manual de estos archivos sea propensa a errores. Como alternativa, puede crear archivos .resx mediante programación con tipos y miembros de la biblioteca de clases .NET Framework. También puede usar la biblioteca de clases .NET Framework para recuperar los recursos almacenados en archivos .resx. En este artículo se explica cómo puede <xref:System.Resources> usar los tipos y miembros del espacio de nombres para trabajar con archivos .resx.

En este artículo se describe cómo trabajar con archivos XML (.resx) que contienen recursos. Para obtener información sobre cómo trabajar con archivos de <xref:System.Resources.ResourceManager>recursos binarios que se han incrustado en ensamblados, vea .

> [!WARNING]
> También hay formas distintas para trabajar con archivos .resx que no son mediante programación. Al agregar un archivo de recursos a un proyecto de [Visual Studio,](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) Visual Studio proporciona una interfaz para crear y mantener un archivo .resx y convierte automáticamente el archivo .resx en un archivo .resources en tiempo de compilación. También puede utilizar un editor de texto para manipular un archivo .resx directamente. Sin embargo, para evitar que se dañe el archivo, tenga cuidado de no modificar la información binaria almacenada en el archivo.

## <a name="create-a-resx-file"></a>Creación de un archivo .resx

Puede utilizar la clase <xref:System.Resources.ResXResourceWriter?displayProperty=nameWithType> para crear un archivo .resx mediante programación, siga estos pasos:

1. Cree una instancia de un objeto <xref:System.Resources.ResXResourceWriter> mediante una llamada al método <xref:System.Resources.ResXResourceWriter.%23ctor%28System.String%29> y facilite el nombre del archivo .resx. El nombre de archivo debe incluir la extensión .resx. Si crea una instancia del objeto <xref:System.Resources.ResXResourceWriter> en un bloque `using` , no es necesario que llame explícitamente al método <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> en el paso 3.

2. Llame al método <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> para cada recurso que quiera agregar al archivo. Utilice las sobrecargas de este método para agregar datos binarios (matriz de bytes), de objeto y de cadena. Si el recurso es un objeto, debe ser serializable.

3. Llame al método <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> para generar el archivo de recursos y liberar todos los recursos. Si el objeto <xref:System.Resources.ResXResourceWriter> se creó dentro de un bloque `using` , los recursos se escriben en el archivo .resx y los que utiliza el objeto <xref:System.Resources.ResXResourceWriter> se liberan al final del bloque `using` .

El archivo .resx resultante tiene el encabezado adecuado y una etiqueta `data` por cada recurso que agregó el método <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> .

> [!WARNING]
> No utilice archivos de recursos para almacenar contraseñas, información relativa a la seguridad o datos privados.

En el ejemplo siguiente se crea un archivo .resx denominado CarResources.resx que almacena seis cadenas, un icono y dos objetos definidos por la aplicación (dos objetos `Automobile` ). La `Automobile` clase, que se define y crea una <xref:System.SerializableAttribute> instancia en el ejemplo, se etiqueta con el atributo.

[!code-csharp[Conceptual.Resources.ResX#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resx/cs/create1.cs#1)]
[!code-vb[Conceptual.Resources.ResX#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resx/vb/create1.vb#1)]

> [!TIP]
> También puede usar [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) para crear archivos .resx. En tiempo de compilación, Visual Studio utiliza el [generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) para convertir el archivo .resx en un archivo de recursos binario (.resources) y también lo inserta en un ensamblado de aplicación o un ensamblado satélite.

No se puede insertar un archivo .resx en un archivo ejecutable en tiempo de ejecución ni compilarlo en un ensamblado satélite. Debe convertir el archivo .resx en un archivo de recursos binario (.resources) con el [generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md). El archivo .resources resultante puede entonces insertarse en un ensamblado de aplicación o un ensamblado satélite. Para obtener más información, consulta [Creating Resource Files](creating-resource-files-for-desktop-apps.md).

## <a name="enumerate-resources"></a>Enumeración de los recursos
 En algunos casos, quizás quiera recuperar todos los recursos de un archivo .resx, en lugar de un recurso concreto. Para ello, puede utilizar la clase <xref:System.Resources.ResXResourceReader?displayProperty=nameWithType> , que ofrece un enumerador para todos los recursos del archivo .resx. La clase <xref:System.Resources.ResXResourceReader?displayProperty=nameWithType> implementa <xref:System.Collections.IDictionaryEnumerator>, que devuelve un objeto <xref:System.Collections.DictionaryEntry> que representa un recurso concreto para cada iteración del bucle. Su propiedad <xref:System.Collections.DictionaryEntry.Key%2A?displayProperty=nameWithType> devuelve la clave del recurso y su propiedad <xref:System.Collections.DictionaryEntry.Value%2A?displayProperty=nameWithType> devuelve el valor del recurso.

 En el ejemplo siguiente, se crea un objeto <xref:System.Resources.ResXResourceReader> para el archivo CarResources.resx creado en el ejemplo anterior y se recorre iterativamente el archivo de recursos. Se agregan los dos objetos `Automobile` que están definidos en el archivo de recursos para un objeto <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> y se agregan cinco de las seis cadenas a un objeto <xref:System.Collections.SortedList> . Los valores del objeto <xref:System.Collections.SortedList> se convierten en una matriz de parámetros, que se utiliza para mostrar los encabezados de columna en la consola. Los valores de propiedad `Automobile` también se muestran en la consola.

 [!code-csharp[Conceptual.Resources.ResX#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resx/cs/enumerate1.cs#2)]
 [!code-vb[Conceptual.Resources.ResX#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resx/vb/enumerate1.vb#2)]

## <a name="retrieve-a-specific-resource"></a>Recuperación de un recurso concreto
 Además de enumerar los elementos de un archivo .resx, puede recuperar un recurso concreto por su nombre con la clase <xref:System.Resources.ResXResourceSet?displayProperty=nameWithType> . El método <xref:System.Resources.ResourceSet.GetString%28System.String%29?displayProperty=nameWithType> recupera el valor de un recurso de cadena con nombre. El método <xref:System.Resources.ResourceSet.GetObject%28System.String%29?displayProperty=nameWithType> recupera el valor de datos binarios o un objeto con nombre. El método devuelve un objeto que se debe convertir en un objeto del tipo adecuado.

 En el ejemplo siguiente se recupera la cadena de título de un formulario y el icono por sus nombres de recursos. También se recuperan los objetos `Automobile` definidos por la aplicación que se usan en el ejemplo anterior y se muestran en un control <xref:System.Windows.Forms.DataGridView>.

 [!code-csharp[Conceptual.Resources.ResX#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resx/cs/retrieve1.cs#3)]
 [!code-vb[Conceptual.Resources.ResX#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resx/vb/retrieve1.vb#3)]

## <a name="convert-resx-files-to-binary-resources-files"></a>Conversión de archivos .resx en archivos .resources binarios
 La conversión de archivos .resx en archivos de recursos binario (.resources) insertados tiene ventajas importantes. Aunque los archivos .resx son fáciles de leer y mantener durante el desarrollo de aplicaciones, en rara ocasión se incluyen con las aplicaciones terminadas. Si se distribuyen con una aplicación, son archivos independientes separados del ejecutable de la aplicación y las bibliotecas que lo acompañan. En cambio, los archivos .resources se insertan en el archivo ejecutable de la aplicación o en los ensamblados que lo acompañan. Además, en las aplicaciones localizadas, al depender de archivos .resx en tiempo de ejecución, la responsabilidad de controlar la reserva de recursos es del desarrollador. En cambio, si se creó un conjunto de ensamblados satélite que contienen archivos .resources insertados, Common Language Runtime administra el proceso de reserva de recursos.

 Para convertir un archivo .resx en un archivo .resources, utilice el [generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md), que tiene la siguiente sintaxis básica:

 **Resgen.exe** *nombreArchivo.resx*

 El resultado es un archivo de recursos binario que tiene el mismo nombre de archivo raíz que el archivo .resx y una extensión de archivo .resources. Este archivo puede compilarse en un archivo ejecutable o una biblioteca en tiempo de compilación. Si está utilizando el compilador de Visual Basic, use la siguiente sintaxis para insertar un archivo .resources en el archivo ejecutable de la aplicación:

 **vbc** *nombreArchivo* **.vb -resource:** *nombreArchivo.resources*

 Si está utilizando C#, la sintaxis es la que se indica a continuación:

 **csc** *nombreArchivo* **.cs -resource:** *nombreArchivo.resources*

 También se puede insertar el archivo .resources en un ensamblado satélite con [Assembly Linker (AL.exe)](../tools/al-exe-assembly-linker.md), que tiene la siguiente sintaxis básica:

 **al** *nombreArchivoRecursos* **-out:** *nombreArchivoEnsamblado*

## <a name="see-also"></a>Consulte también

- [Crear archivos de recursos](creating-resource-files-for-desktop-apps.md)
- [Resgen.exe (Generador de archivos de recursos)](../tools/resgen-exe-resource-file-generator.md)
- [Al.exe (Enlazador de ensamblajes)](../tools/al-exe-assembly-linker.md)
