---
title: Convertir cadenas en tipos de datos de .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce594234e601cd8feb4723bbc383db9e3ed40522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="converting-strings-to-net-framework-data-types"></a><span data-ttu-id="d1c49-102">Convertir cadenas en tipos de datos de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d1c49-102">Converting Strings to .NET Framework Data Types</span></span>
<span data-ttu-id="d1c49-103">Si desea convertir una cadena en un tipo de datos de .NET Framework, use la **XmlConvert** método que se adapte a los requisitos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d1c49-103">If you want to convert a string to a .NET Framework data type, use the **XmlConvert** method that fits the application requirements.</span></span> <span data-ttu-id="d1c49-104">Para obtener una lista de todos los métodos de conversión disponibles en la **XmlConvert** de clases, consulte <xref:System.Xml.XmlConvert>.</span><span class="sxs-lookup"><span data-stu-id="d1c49-104">For a list of all conversion methods available in the **XmlConvert** class, see <xref:System.Xml.XmlConvert>.</span></span>  
  
 <span data-ttu-id="d1c49-105">La cadena devuelta de la **ToString** método es una versión de cadena de los datos que se pasan.</span><span class="sxs-lookup"><span data-stu-id="d1c49-105">The string returned from the **ToString** method is a string version of the data that is passed in.</span></span> <span data-ttu-id="d1c49-106">Además, hay varios tipos de .NET Framework que realizan la conversión mediante la **XmlConvert** clase, pero no utilizan los métodos de la **System.Convert** clase.</span><span class="sxs-lookup"><span data-stu-id="d1c49-106">Additionally, there are several .NET Framework types that convert using the **XmlConvert** class yet they do not use the methods in the **System.Convert** class.</span></span> <span data-ttu-id="d1c49-107">El **XmlConvert** clase sigue la especificación de tipo de datos de esquemas XML (XSD) y tienen un tipo que el **XmlConvert** puede asignar a.</span><span class="sxs-lookup"><span data-stu-id="d1c49-107">The **XmlConvert** class follows the XML Schema (XSD) data type specification and has a data type that the **XmlConvert** can map to.</span></span>  
  
 <span data-ttu-id="d1c49-108">En la tabla siguiente se enumeran los tipos de datos de .NET Framework y los tipos de cadena que se devuelven mediante la asignación de tipos de datos de los esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="d1c49-108">The following table lists .NET Framework data types and the string types that are returned using XML Schema (XSD) data type mapping.</span></span> <span data-ttu-id="d1c49-109">No se puede procesar estos tipos de .NET Framework mediante **System.Convert**.</span><span class="sxs-lookup"><span data-stu-id="d1c49-109">These .NET Framework types cannot be processed using **System.Convert**.</span></span>  
  
|<span data-ttu-id="d1c49-110">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d1c49-110">.NET Framework type</span></span>|<span data-ttu-id="d1c49-111">Cadena devuelta</span><span class="sxs-lookup"><span data-stu-id="d1c49-111">String returned</span></span>|  
|-------------------------|---------------------|  
|<span data-ttu-id="d1c49-112">Boolean</span><span class="sxs-lookup"><span data-stu-id="d1c49-112">Boolean</span></span>|<span data-ttu-id="d1c49-113">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="d1c49-113">"true", "false"</span></span>|  
|<span data-ttu-id="d1c49-114">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="d1c49-114">Single.PositiveInfinity</span></span>|<span data-ttu-id="d1c49-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="d1c49-115">"INF"</span></span>|  
|<span data-ttu-id="d1c49-116">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="d1c49-116">Single.NegativeInfinity</span></span>|<span data-ttu-id="d1c49-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="d1c49-117">"-INF"</span></span>|  
|<span data-ttu-id="d1c49-118">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="d1c49-118">Double.PositiveInfinity</span></span>|<span data-ttu-id="d1c49-119">"INF"</span><span class="sxs-lookup"><span data-stu-id="d1c49-119">"INF"</span></span>|  
|<span data-ttu-id="d1c49-120">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="d1c49-120">Double.NegativeInfinity</span></span>|<span data-ttu-id="d1c49-121">"-INF"</span><span class="sxs-lookup"><span data-stu-id="d1c49-121">"-INF"</span></span>|  
|<span data-ttu-id="d1c49-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="d1c49-122">DateTime</span></span>|<span data-ttu-id="d1c49-123">El formato es "aaaa-MM-ddTHH:mm:sszzzzzz" y sus subconjuntos.</span><span class="sxs-lookup"><span data-stu-id="d1c49-123">Format is "yyyy-MM-ddTHH:mm:sszzzzzz" and its subsets.</span></span>|  
|<span data-ttu-id="d1c49-124">Timespan</span><span class="sxs-lookup"><span data-stu-id="d1c49-124">Timespan</span></span>|<span data-ttu-id="d1c49-125">El formato es PnYnMnTnHnMnS, es decir, `P2Y10M15DT10H30M20S` corresponde a una duración de 2 años, 10 meses, 15 días, 10 horas, 30 minutos y 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="d1c49-125">Format is PnYnMnTnHnMnS that is, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10 hours, 30 minutes, and 20 seconds.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d1c49-126">Si se convierte uno de los tipos de .NET Framework enumerados en la tabla en una cadena mediante el **ToString** método, la cadena devuelta no es el tipo base, pero el tipo de cadena de esquema XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="d1c49-126">If converting any of the .NET Framework types listed in the table to a string using the **ToString** method, the returned string is not the base type, but the XML Schema (XSD) string type.</span></span>  
  
 <span data-ttu-id="d1c49-127">El **DateTime** y **Timespan** difiere del tipo de valor en el que un **DateTime** representa un instante de tiempo, mientras que un **TimeSpan** Representa un intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="d1c49-127">The **DateTime** and **Timespan** value type differs in that a **DateTime** represents an instant in time, whereas a **TimeSpan** represents a time interval.</span></span> <span data-ttu-id="d1c49-128">El **DateTime** y **Timespan** formatos se especifican en la especificación de tipos de datos de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="d1c49-128">The **DateTime** and **Timespan** formats are specified in the XML Schema (XSD) data types specification.</span></span> <span data-ttu-id="d1c49-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d1c49-129">For example:</span></span>  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim [date] As New DateTime(2001, 8, 4)  
writer.WriteElementString("Date", XmlConvert.ToString([date]))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
DateTime date = new DateTime (2001, 08, 04);  
writer.WriteElementString("Date", XmlConvert.ToString(date));  
```  
  
 <span data-ttu-id="d1c49-130">**Salida**</span><span class="sxs-lookup"><span data-stu-id="d1c49-130">**Output**</span></span>  
  
 <span data-ttu-id="d1c49-131">`<Date>2001-08-04T00:00:00</Date>`.</span><span class="sxs-lookup"><span data-stu-id="d1c49-131">`<Date>2001-08-04T00:00:00</Date>`.</span></span>  
  
 <span data-ttu-id="d1c49-132">En el código siguiente se convierte un número entero en una cadena:</span><span class="sxs-lookup"><span data-stu-id="d1c49-132">The following code converts an integer to a string:</span></span>  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim value As Int32 = 200  
writer.WriteElementString("Number", XmlConvert.ToString(value))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
Int32 value = 200;  
writer.WriteElementString("Number", XmlConvert.ToString(value));  
```  
  
 <span data-ttu-id="d1c49-133">**Salida**</span><span class="sxs-lookup"><span data-stu-id="d1c49-133">**Output**</span></span>  
  
 `<Number>200</Number>`  
  
 <span data-ttu-id="d1c49-134">Sin embargo, si va a convertir una cadena a **booleano**, **único**, o **doble**, el tipo de .NET Framework que se devuelve no es el mismo que el tipo devuelto al utilizar la **System.Convert** clase.</span><span class="sxs-lookup"><span data-stu-id="d1c49-134">However, if you are converting a string to **Boolean**, **Single**, or **Double**, the .NET Framework type that is returned is not the same as the type returned when using the **System.Convert** class.</span></span>  
  
## <a name="string-to-boolean"></a><span data-ttu-id="d1c49-135">Conversión de cadenas en Boolean</span><span class="sxs-lookup"><span data-stu-id="d1c49-135">String to Boolean</span></span>  
 <span data-ttu-id="d1c49-136">En la tabla siguiente se muestra qué tipo se genera para las cadenas de entrada dadas, al convertir una cadena en **booleano** mediante la **ToBoolean** método.</span><span class="sxs-lookup"><span data-stu-id="d1c49-136">The following table shows what type is generated for the given input strings, when converting a string to **Boolean** using the **ToBoolean** method.</span></span>  
  
|<span data-ttu-id="d1c49-137">Parámetro de entrada de cadena válido</span><span class="sxs-lookup"><span data-stu-id="d1c49-137">Valid string input parameter</span></span>|<span data-ttu-id="d1c49-138">Tipo de salida de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d1c49-138">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="d1c49-139">"true"</span><span class="sxs-lookup"><span data-stu-id="d1c49-139">"true"</span></span>|<span data-ttu-id="d1c49-140">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="d1c49-140">Boolean.True</span></span>|  
|<span data-ttu-id="d1c49-141">"1"</span><span class="sxs-lookup"><span data-stu-id="d1c49-141">"1"</span></span>|<span data-ttu-id="d1c49-142">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="d1c49-142">Boolean.True</span></span>|  
|<span data-ttu-id="d1c49-143">"false"</span><span class="sxs-lookup"><span data-stu-id="d1c49-143">"false"</span></span>|<span data-ttu-id="d1c49-144">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="d1c49-144">Boolean.False</span></span>|  
|<span data-ttu-id="d1c49-145">"0"</span><span class="sxs-lookup"><span data-stu-id="d1c49-145">"0"</span></span>|<span data-ttu-id="d1c49-146">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="d1c49-146">Boolean.False</span></span>|  
  
 <span data-ttu-id="d1c49-147">Por ejemplo, dado el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="d1c49-147">For example, given the following XML:</span></span>  
  
 <span data-ttu-id="d1c49-148">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="d1c49-148">**Input**</span></span>  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>   
```  
  
 <span data-ttu-id="d1c49-149">El código siguiente pueden entender ambas y **bvalue** es **System.Boolean.True**:</span><span class="sxs-lookup"><span data-stu-id="d1c49-149">Both can be understood by the following code, and **bvalue** is **System.Boolean.True**:</span></span>  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a><span data-ttu-id="d1c49-150">Conversión de cadenas en Single</span><span class="sxs-lookup"><span data-stu-id="d1c49-150">String to Single</span></span>  
 <span data-ttu-id="d1c49-151">En la tabla siguiente se muestra qué tipo se genera para las cadenas de entrada dadas, al convertir una cadena en un **único** mediante la **ToSingle** método.</span><span class="sxs-lookup"><span data-stu-id="d1c49-151">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToSingle** method.</span></span>  
  
|<span data-ttu-id="d1c49-152">Parámetro de entrada de cadena válido</span><span class="sxs-lookup"><span data-stu-id="d1c49-152">Valid string input parameter</span></span>|<span data-ttu-id="d1c49-153">Tipo de salida de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d1c49-153">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="d1c49-154">"INF"</span><span class="sxs-lookup"><span data-stu-id="d1c49-154">"INF"</span></span>|<span data-ttu-id="d1c49-155">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="d1c49-155">Single.PositiveInfinity</span></span>|  
|<span data-ttu-id="d1c49-156">"-INF"</span><span class="sxs-lookup"><span data-stu-id="d1c49-156">"-INF"</span></span>|<span data-ttu-id="d1c49-157">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="d1c49-157">Single.NegativeInfinity</span></span>|  
  
## <a name="string-to-double"></a><span data-ttu-id="d1c49-158">Conversión de cadenas en Double</span><span class="sxs-lookup"><span data-stu-id="d1c49-158">String to Double</span></span>  
 <span data-ttu-id="d1c49-159">En la tabla siguiente se muestra qué tipo se genera para las cadenas de entrada dadas, al convertir una cadena en un **único** mediante la **ToDouble** método.</span><span class="sxs-lookup"><span data-stu-id="d1c49-159">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToDouble** method.</span></span>  
  
|<span data-ttu-id="d1c49-160">Parámetro de entrada de cadena válido</span><span class="sxs-lookup"><span data-stu-id="d1c49-160">Valid string input parameter</span></span>|<span data-ttu-id="d1c49-161">Tipo de salida de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d1c49-161">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="d1c49-162">"INF"</span><span class="sxs-lookup"><span data-stu-id="d1c49-162">"INF"</span></span>|<span data-ttu-id="d1c49-163">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="d1c49-163">Double.PositiveInfinity</span></span>|  
|<span data-ttu-id="d1c49-164">"-INF"</span><span class="sxs-lookup"><span data-stu-id="d1c49-164">"-INF"</span></span>|<span data-ttu-id="d1c49-165">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="d1c49-165">Double.NegativeInfinity</span></span>|  
  
 <span data-ttu-id="d1c49-166">El código siguiente escribe `<Infinity>INF</Infinity>`:</span><span class="sxs-lookup"><span data-stu-id="d1c49-166">The following code writes `<Infinity>INF</Infinity>`:</span></span>  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1c49-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1c49-167">See Also</span></span>  
 [<span data-ttu-id="d1c49-168">Conversión de tipos de datos XML</span><span class="sxs-lookup"><span data-stu-id="d1c49-168">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="d1c49-169">Convertir tipos de .NET Framework en cadenas</span><span class="sxs-lookup"><span data-stu-id="d1c49-169">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
