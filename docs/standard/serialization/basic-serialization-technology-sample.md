---
title: Ejemplo de tecnología de serialización básica
description: En este ejemplo se demuestra la capacidad de CLR para serializar un gráfico de objetos en memoria en una secuencia. En él se puede usar SoapFormatter o BinaryFormatter.
ms.date: 03/30/2017
ms.assetid: 9d824e16-08d1-4a36-bc7f-2388c1f75f34
ms.openlocfilehash: fcbf790c3b3d48a0aeb27fd1ef6f75dcd7609ae0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378440"
---
# <a name="basic-serialization-technology-sample"></a>Ejemplo de tecnología de serialización básica

[Descargar ejemplo](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)

En este ejemplo se demuestra la capacidad de Common Language Runtime para serializar un gráfico de objetos de la memoria en una secuencia. En este ejemplo se puede utilizar <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para la serialización. Se serializa o deserializa una lista vinculada, llena de datos, desde o hacia una secuencia del archivo. En cualquier caso, se muestra la lista para que pueda ver los resultados. La lista vinculada es de tipo `LinkedList`, un tipo definido por este ejemplo.

Para obtener más información sobre la serialización, revise los comentarios de los archivos de código fuente y de build.proj.

### <a name="to-build-the-sample-using-the-command-prompt"></a>Para generar el ejemplo desde el símbolo del sistema

1. Navegue hasta uno de los subdirectorios específicos de lenguaje bajo el directorio Technologies\Serialization\Runtime Serialization\Basic, utilizando el símbolo del sistema.

2. Escriba **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** o **msbuild SerializationVB.sln**, según el lenguaje de programación que prefiera, en la línea de comandos.

### <a name="to-build-the-sample-using-visual-studio"></a>Para compilar el ejemplo con Visual Studio

1. Abra el Explorador de archivos y navegue hasta uno de los subdirectorios específicos del lenguaje del ejemplo.

2. Haga doble clic en el icono del archivo SerializationCS.sln, SerializationJSL.sln o SerializationVB.sln, dependiendo del lenguaje de programación elegido, para abrir el archivo en Visual Studio.

3. En el menú **Compilar**, seleccione **Compilar solución**.

 La aplicación de ejemplo se generará en el subdirectorio predeterminado \bin o \bin\Debug.

### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo

1. Navegue hasta el directorio que contiene el ejecutable generado.

2. Escriba **Serialization.exe**, junto con los valores de parámetro que quiera, en la línea de comandos.

  > [!NOTE]
  > En este ejemplo se genera una aplicación de consola. Para poder ver el resultado, debe iniciarla desde la línea de comandos.

## <a name="remarks"></a>Comentarios

La aplicación de ejemplo acepta parámetros de línea de comandos que indican qué comprobación desea ejecutar. Para serializar una lista de 10 nodos en un archivo denominado **Test.xml** mediante el formateador SOAP, use los parámetros **sx Test.xml 10**.

Por ejemplo:

```console
Serialize.exe -sx Test.xml 10
```

Para deserializar el archivo **Test.xml** del ejemplo anterior, use los parámetros **dx Test.xml**.

Por ejemplo:

```console
Serialize.exe -dx Test.xml
```

En los dos ejemplos anteriores, la "x" en el modificador de la línea de comandos indica que desea realizar una serialización de XML SOAP. Puede utilizar "b" en su lugar para utilizar la serialización binaria. Si desea realizar la serialización con un gran número de nodos, puede que prefiera redirigir el resultado de la consola a un archivo.

Por ejemplo:

```console
Serialize.exe -sb Test.bin 10000 >somefile.txt
```

Las viñetas siguientes describen brevemente las clases y las tecnologías que se utilizan en este ejemplo.

- Serialización en tiempo de ejecución

  - <xref:System.Runtime.Serialization.IFormatter> Se usa para hacer referencia a un objeto <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.

  - <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Se usa para serializar una lista vinculada a una secuencia en formato binario. El formateador binario utiliza un formato que solo entiende el tipo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. Sin embargo, los datos son concisos.

  - <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Se usa para serializar una lista vinculada a una secuencia en formato SOAP. SOAP es un formato estándar.

- E/S de secuencia

  - <xref:System.IO.Stream> Se utiliza para serializar y deserializar. El tipo de secuencia concreto utilizado en este ejemplo es el tipo <xref:System.IO.FileStream>. Sin embargo, la serialización se puede utilizar con cualquier tipo derivado de <xref:System.IO.Stream>.

  - <xref:System.IO.File> Se utiliza para crear objetos <xref:System.IO.FileStream> para leer y crear archivos en disco.

  - <xref:System.IO.FileStream> Se utiliza para serializar y deserializar las listas vinculadas.

## <a name="see-also"></a>Vea también

- <xref:System.IO>
- <xref:System.IO.File>
- <xref:System.IO.FileStream>
- <xref:System.IO.Stream>
- <xref:System.Random>
- <xref:System.Runtime.Serialization>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
- <xref:System.Runtime.Serialization.IFormatter>
- <xref:System.SerializableAttribute>
- <xref:System.Xml.Serialization>
- [Serialización básica](../../../docs/standard/serialization/basic-serialization.md)
- [Serialización binaria](../../../docs/standard/serialization/binary-serialization.md)
- [Controlar la serialización XML mediante atributos](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [Introducción a la serialización XML](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [Serialización](../../../docs/standard/serialization/index.md)
- [Serialización SOAP y XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)
