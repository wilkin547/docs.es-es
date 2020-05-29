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
# <a name="basic-serialization-technology-sample"></a><span data-ttu-id="4c3b5-104">Ejemplo de tecnología de serialización básica</span><span class="sxs-lookup"><span data-stu-id="4c3b5-104">Basic Serialization Technology Sample</span></span>

[<span data-ttu-id="4c3b5-105">Descargar ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c3b5-105">Download sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)

<span data-ttu-id="4c3b5-106">En este ejemplo se demuestra la capacidad de Common Language Runtime para serializar un gráfico de objetos de la memoria en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-106">This sample demonstrates the common language runtime's ability to serialize an object graph in memory to a stream.</span></span> <span data-ttu-id="4c3b5-107">En este ejemplo se puede utilizar <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para la serialización.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-107">This sample can use either the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> or the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> for serialization.</span></span> <span data-ttu-id="4c3b5-108">Se serializa o deserializa una lista vinculada, llena de datos, desde o hacia una secuencia del archivo.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-108">A linked list, filled with data, is serialized or deserialized to or from a file stream.</span></span> <span data-ttu-id="4c3b5-109">En cualquier caso, se muestra la lista para que pueda ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-109">In either case the list is displayed so that you can see the results.</span></span> <span data-ttu-id="4c3b5-110">La lista vinculada es de tipo `LinkedList`, un tipo definido por este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-110">The linked list is of type `LinkedList`, a type defined by this sample.</span></span>

<span data-ttu-id="4c3b5-111">Para obtener más información sobre la serialización, revise los comentarios de los archivos de código fuente y de build.proj.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-111">Review comments in the source code and build.proj files for more information on serialization.</span></span>

### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="4c3b5-112">Para generar el ejemplo desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="4c3b5-112">To build the sample using the Command Prompt</span></span>

1. <span data-ttu-id="4c3b5-113">Navegue hasta uno de los subdirectorios específicos de lenguaje bajo el directorio Technologies\Serialization\Runtime Serialization\Basic, utilizando el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-113">Navigate to one of the language-specific subdirectories under the Technologies\Serialization\Runtime Serialization\Basic directory, using the command prompt.</span></span>

2. <span data-ttu-id="4c3b5-114">Escriba **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** o **msbuild SerializationVB.sln**, según el lenguaje de programación que prefiera, en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-114">Type **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** or **msbuild SerializationVB.sln**, depending on your choice of programming language, at the command line.</span></span>

### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="4c3b5-115">Para compilar el ejemplo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4c3b5-115">To build the sample using Visual Studio</span></span>

1. <span data-ttu-id="4c3b5-116">Abra el Explorador de archivos y navegue hasta uno de los subdirectorios específicos del lenguaje del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-116">Open File Explorer and navigate to one of the language-specific subdirectories for the sample.</span></span>

2. <span data-ttu-id="4c3b5-117">Haga doble clic en el icono del archivo SerializationCS.sln, SerializationJSL.sln o SerializationVB.sln, dependiendo del lenguaje de programación elegido, para abrir el archivo en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-117">Double-click the icon for the SerializationCS.sln, SerializationJSL.sln or SerializationVB.sln file, depending on your choice of programming language, to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="4c3b5-118">En el menú **Compilar**, seleccione **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-118">In the **Build** menu, select **Build Solution**.</span></span>

 <span data-ttu-id="4c3b5-119">La aplicación de ejemplo se generará en el subdirectorio predeterminado \bin o \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-119">The sample application will be built in the default \bin or \bin\Debug subdirectory.</span></span>

### <a name="to-run-the-sample"></a><span data-ttu-id="4c3b5-120">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c3b5-120">To run the sample</span></span>

1. <span data-ttu-id="4c3b5-121">Navegue hasta el directorio que contiene el ejecutable generado.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-121">Navigate to the directory containing the built executable.</span></span>

2. <span data-ttu-id="4c3b5-122">Escriba **Serialization.exe**, junto con los valores de parámetro que quiera, en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-122">Type **Serialization.exe**, along with the parameter values you desire, at the command line.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4c3b5-123">En este ejemplo se genera una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-123">This sample builds a console application.</span></span> <span data-ttu-id="4c3b5-124">Para poder ver el resultado, debe iniciarla desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-124">You must launch it using the command prompt in order to view its output.</span></span>

## <a name="remarks"></a><span data-ttu-id="4c3b5-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4c3b5-125">Remarks</span></span>

<span data-ttu-id="4c3b5-126">La aplicación de ejemplo acepta parámetros de línea de comandos que indican qué comprobación desea ejecutar.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-126">The sample application accepts command line parameters indicating which test you would like to execute.</span></span> <span data-ttu-id="4c3b5-127">Para serializar una lista de 10 nodos en un archivo denominado **Test.xml** mediante el formateador SOAP, use los parámetros **sx Test.xml 10**.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-127">To serialize a 10-node list to a file named **Test.xml** using the SOAP formatter, use the parameters **sx Test.xml 10**.</span></span>

<span data-ttu-id="4c3b5-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4c3b5-128">For Example:</span></span>

```console
Serialize.exe -sx Test.xml 10
```

<span data-ttu-id="4c3b5-129">Para deserializar el archivo **Test.xml** del ejemplo anterior, use los parámetros **dx Test.xml**.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-129">To deserialize the **Test.xml** file from the previous example, use the parameters **dx Test.xml**.</span></span>

<span data-ttu-id="4c3b5-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4c3b5-130">For Example:</span></span>

```console
Serialize.exe -dx Test.xml
```

<span data-ttu-id="4c3b5-131">En los dos ejemplos anteriores, la "x" en el modificador de la línea de comandos indica que desea realizar una serialización de XML SOAP.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-131">In the two examples above, the "x" in the command line switch indicates that you want XML SOAP serialization.</span></span> <span data-ttu-id="4c3b5-132">Puede utilizar "b" en su lugar para utilizar la serialización binaria.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-132">You can use "b" in its place to use binary serialization.</span></span> <span data-ttu-id="4c3b5-133">Si desea realizar la serialización con un gran número de nodos, puede que prefiera redirigir el resultado de la consola a un archivo.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-133">If you wish to try serialization with a very large number of nodes, you might want to redirect the console output to a file.</span></span>

<span data-ttu-id="4c3b5-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4c3b5-134">For Example:</span></span>

```console
Serialize.exe -sb Test.bin 10000 >somefile.txt
```

<span data-ttu-id="4c3b5-135">Las viñetas siguientes describen brevemente las clases y las tecnologías que se utilizan en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-135">The following bullets briefly describe the classes and technologies used by this sample.</span></span>

- <span data-ttu-id="4c3b5-136">Serialización en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4c3b5-136">Runtime Serialization</span></span>

  - <span data-ttu-id="4c3b5-137"><xref:System.Runtime.Serialization.IFormatter> Se usa para hacer referencia a un objeto <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-137"><xref:System.Runtime.Serialization.IFormatter> Used to refer to either a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or a <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> object.</span></span>

  - <span data-ttu-id="4c3b5-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Se usa para serializar una lista vinculada a una secuencia en formato binario.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Used to serialize a linked list to a stream in a binary format.</span></span> <span data-ttu-id="4c3b5-139">El formateador binario utiliza un formato que solo entiende el tipo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-139">The binary formatter uses a format that only the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> type understands.</span></span> <span data-ttu-id="4c3b5-140">Sin embargo, los datos son concisos.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-140">However, the data is concise.</span></span>

  - <span data-ttu-id="4c3b5-141"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Se usa para serializar una lista vinculada a una secuencia en formato SOAP.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-141"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Used to serialize a linked list to a stream in the SOAP format.</span></span> <span data-ttu-id="4c3b5-142">SOAP es un formato estándar.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-142">SOAP is a standard format.</span></span>

- <span data-ttu-id="4c3b5-143">E/S de secuencia</span><span class="sxs-lookup"><span data-stu-id="4c3b5-143">Stream I/O</span></span>

  - <span data-ttu-id="4c3b5-144"><xref:System.IO.Stream> Se utiliza para serializar y deserializar.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-144"><xref:System.IO.Stream> Used to serialize and deserialize.</span></span> <span data-ttu-id="4c3b5-145">El tipo de secuencia concreto utilizado en este ejemplo es el tipo <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-145">The specific stream type used in this sample is the <xref:System.IO.FileStream> type.</span></span> <span data-ttu-id="4c3b5-146">Sin embargo, la serialización se puede utilizar con cualquier tipo derivado de <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-146">However, serialization can be used with any type derived from <xref:System.IO.Stream>.</span></span>

  - <span data-ttu-id="4c3b5-147"><xref:System.IO.File> Se utiliza para crear objetos <xref:System.IO.FileStream> para leer y crear archivos en disco.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-147"><xref:System.IO.File> Used to create <xref:System.IO.FileStream> objects for reading and creating files on disk.</span></span>

  - <span data-ttu-id="4c3b5-148"><xref:System.IO.FileStream> Se utiliza para serializar y deserializar las listas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="4c3b5-148"><xref:System.IO.FileStream> Used to serialize and deserialize linked lists.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c3b5-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c3b5-149">See also</span></span>

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
- [<span data-ttu-id="4c3b5-150">Serialización básica</span><span class="sxs-lookup"><span data-stu-id="4c3b5-150">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)
- [<span data-ttu-id="4c3b5-151">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="4c3b5-151">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)
- [<span data-ttu-id="4c3b5-152">Controlar la serialización XML mediante atributos</span><span class="sxs-lookup"><span data-stu-id="4c3b5-152">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [<span data-ttu-id="4c3b5-153">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="4c3b5-153">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="4c3b5-154">Serialización</span><span class="sxs-lookup"><span data-stu-id="4c3b5-154">Serialization</span></span>](../../../docs/standard/serialization/index.md)
- [<span data-ttu-id="4c3b5-155">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="4c3b5-155">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
