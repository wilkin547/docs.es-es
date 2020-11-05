---
title: Creación de aplicaciones de consola en .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, creating console applications
- application development [.NET], console
- console applications
ms.assetid: c21fb997-9f0e-40a5-8741-f73bba376bd8
ms.openlocfilehash: b9c38e1311379037695879565b33ade29c6bf632
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687545"
---
# <a name="console-apps-in-net"></a>Aplicaciones de consola en .NET

Las aplicaciones de .NET pueden usar la clase <xref:System.Console?displayProperty=nameWithType> para leer y escribir caracteres en la consola. Los datos de la consola se leen desde el flujo de entrada estándar, los datos de la consola se escriben en el flujo de salida estándar y los datos de error de la consola se escriben en el flujo de salida de error estándar. Estos flujos se asocian automáticamente a la consola cuando se inicia la aplicación y se presentan como las propiedades <xref:System.Console.In%2A>, <xref:System.Console.Out%2A> y <xref:System.Console.Error%2A>, respectivamente.

El valor de la propiedad <xref:System.Console.In%2A?displayProperty=nameWithType> es un objeto <xref:System.IO.TextReader?displayProperty=nameWithType>, mientras que los valores de las propiedades <xref:System.Console.Out%2A?displayProperty=nameWithType> y <xref:System.Console.Error%2A?displayProperty=nameWithType> son objetos <xref:System.IO.TextWriter?displayProperty=nameWithType>. Puede asociar estas propiedades a flujos que no representen la consola, lo que le permite hacer que el flujo señale a una ubicación diferente para la entrada o para la salida. Por ejemplo, puede redirigir el resultado a un archivo si establece la propiedad <xref:System.Console.Out%2A?displayProperty=nameWithType> como un <xref:System.IO.StreamWriter?displayProperty=nameWithType>, que encapsula una <xref:System.IO.FileStream?displayProperty=nameWithType> mediante el método <xref:System.Console.SetOut%2A?displayProperty=nameWithType>. Las propiedades <xref:System.Console.In%2A?displayProperty=nameWithType> y <xref:System.Console.Out%2A?displayProperty=nameWithType> no tienen por qué hacer referencia al mismo flujo.

> [!NOTE]
> Para obtener más información sobre cómo compilar aplicaciones de consola, incluidos ejemplos en C#, Visual Basic y C++, vea la documentación de la clase <xref:System.Console>.

Si la consola no existe, como ocurre en una aplicación de Windows Forms, la salida escrita en el flujo de salida estándar no será visible, ya que no hay ninguna consola en la que escribir la información. La escritura de información en una consola inaccesible no provoca una excepción. (Siempre puede cambiar el tipo de aplicación a **Aplicación de consola** , por ejemplo, en las páginas de propiedades del proyecto en Visual Studio).

La clase **System.Console** tiene métodos que pueden leer caracteres individuales o líneas enteras de la consola. Otros métodos convierten datos y cadenas de formato y, después, escriben las cadenas con formato en la consola. Para obtener más información sobre cómo dar formato a las cadenas, vea [Tipos de formato](base-types/formatting-types.md).

> [!TIP]
> Las aplicaciones de consola carecen de un bombeo de mensajes que se inicie de forma predeterminada. Por tanto, las llamadas de la consola a los temporizadores de Microsoft Win32 pueden producir errores.

## <a name="see-also"></a>Vea también

- <xref:System.Console?displayProperty=nameWithType>
- [Aplicación de formato a tipos](base-types/formatting-types.md)
