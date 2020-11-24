---
title: Conversión de cadenas en tipos de datos de .NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
ms.openlocfilehash: 2eee3ff905473d8fd520929c0fe5abfb5d5c42da
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830966"
---
# <a name="convert-strings-to-net-data-types"></a><span data-ttu-id="cb24b-102">Conversión de cadenas en tipos de datos de .NET</span><span class="sxs-lookup"><span data-stu-id="cb24b-102">Convert strings to .NET data types</span></span>

<span data-ttu-id="cb24b-103">Si quiere convertir una cadena en un tipo de datos de .NET, use el método **XmlConvert** que cumple los requisitos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cb24b-103">If you want to convert a string to a .NET data type, use the **XmlConvert** method that fits the application requirements.</span></span> <span data-ttu-id="cb24b-104">Para obtener una lista de los métodos de conversión disponibles en la clase **XmlConvert**, vea <xref:System.Xml.XmlConvert>.</span><span class="sxs-lookup"><span data-stu-id="cb24b-104">For a list of all conversion methods available in the **XmlConvert** class, see <xref:System.Xml.XmlConvert>.</span></span>  
  
 <span data-ttu-id="cb24b-105">La cadena que devuelve el método **ToString** es una versión de cadena de los datos que se le pasan.</span><span class="sxs-lookup"><span data-stu-id="cb24b-105">The string returned from the **ToString** method is a string version of the data that is passed in.</span></span> <span data-ttu-id="cb24b-106">Además, hay varios tipos de .NET que realizan la conversión mediante la clase **XmlConvert**, pero no usan los métodos de la clase **System.Convert**.</span><span class="sxs-lookup"><span data-stu-id="cb24b-106">Additionally, there are several .NET types that convert using the **XmlConvert** class yet they do not use the methods in the **System.Convert** class.</span></span> <span data-ttu-id="cb24b-107">La clase **XmlConvert** sigue la especificación de tipos de datos de los esquemas XML (XSD) y tiene un tipo de datos que se puede asignar en **XmlConvert**.</span><span class="sxs-lookup"><span data-stu-id="cb24b-107">The **XmlConvert** class follows the XML Schema (XSD) data type specification and has a data type that the **XmlConvert** can map to.</span></span>  
  
 <span data-ttu-id="cb24b-108">En la tabla siguiente se enumeran los tipos de datos de .NET y los tipos de cadena que se devuelven mediante la asignación de tipos de datos de los esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="cb24b-108">The following table lists .NET data types and the string types that are returned using XML Schema (XSD) data type mapping.</span></span> <span data-ttu-id="cb24b-109">Estos tipos de .NET no se pueden procesar mediante **System.Convert**.</span><span class="sxs-lookup"><span data-stu-id="cb24b-109">These .NET types cannot be processed using **System.Convert**.</span></span>  
  
|<span data-ttu-id="cb24b-110">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="cb24b-110">.NET type</span></span>|<span data-ttu-id="cb24b-111">Cadena devuelta</span><span class="sxs-lookup"><span data-stu-id="cb24b-111">String returned</span></span>|  
|-------------------------|---------------------|  
|<span data-ttu-id="cb24b-112">Booleano</span><span class="sxs-lookup"><span data-stu-id="cb24b-112">Boolean</span></span>|<span data-ttu-id="cb24b-113">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="cb24b-113">"true", "false"</span></span>|  
|<span data-ttu-id="cb24b-114">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="cb24b-114">Single.PositiveInfinity</span></span>|<span data-ttu-id="cb24b-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="cb24b-115">"INF"</span></span>|  
|<span data-ttu-id="cb24b-116">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="cb24b-116">Single.NegativeInfinity</span></span>|<span data-ttu-id="cb24b-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="cb24b-117">"-INF"</span></span>|  
|<span data-ttu-id="cb24b-118">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="cb24b-118">Double.PositiveInfinity</span></span>|<span data-ttu-id="cb24b-119">"INF"</span><span class="sxs-lookup"><span data-stu-id="cb24b-119">"INF"</span></span>|  
|<span data-ttu-id="cb24b-120">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="cb24b-120">Double.NegativeInfinity</span></span>|<span data-ttu-id="cb24b-121">"-INF"</span><span class="sxs-lookup"><span data-stu-id="cb24b-121">"-INF"</span></span>|  
|<span data-ttu-id="cb24b-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb24b-122">DateTime</span></span>|<span data-ttu-id="cb24b-123">El formato es "aaaa-MM-ddTHH:mm:sszzzzzz" y sus subconjuntos.</span><span class="sxs-lookup"><span data-stu-id="cb24b-123">Format is "yyyy-MM-ddTHH:mm:sszzzzzz" and its subsets.</span></span>|  
|<span data-ttu-id="cb24b-124">Timespan</span><span class="sxs-lookup"><span data-stu-id="cb24b-124">Timespan</span></span>|<span data-ttu-id="cb24b-125">El formato es PnYnMnTnHnMnS, es decir, `P2Y10M15DT10H30M20S` corresponde a una duración de 2 años, 10 meses, 15 días, 10 horas, 30 minutos y 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="cb24b-125">Format is PnYnMnTnHnMnS that is, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10 hours, 30 minutes, and 20 seconds.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="cb24b-126">Si se convierte uno de los tipos de .NET enumerados en la tabla en una cadena mediante el método **ToString**, la cadena devuelta no será el tipo base, sino el tipo de cadena de esquema XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="cb24b-126">If converting any of the .NET types listed in the table to a string using the **ToString** method, the returned string is not the base type, but the XML Schema (XSD) string type.</span></span>  
  
 <span data-ttu-id="cb24b-127">Los tipos de valor de **DateTime** y **Timespan** difieren en que **DateTime** representa un instante en el tiempo, mientras que **TimeSpan** representa un intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="cb24b-127">The **DateTime** and **Timespan** value type differs in that a **DateTime** represents an instant in time, whereas a **TimeSpan** represents a time interval.</span></span> <span data-ttu-id="cb24b-128">Los formatos de **DateTime** y **Timespan** se describen en la especificación de tipos de datos de esquema XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="cb24b-128">The **DateTime** and **Timespan** formats are specified in the XML Schema (XSD) data types specification.</span></span> <span data-ttu-id="cb24b-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cb24b-129">For example:</span></span>  
  
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
  
 <span data-ttu-id="cb24b-130">**Salida**</span><span class="sxs-lookup"><span data-stu-id="cb24b-130">**Output**</span></span>  
  
 <span data-ttu-id="cb24b-131">`<Date>2001-08-04T00:00:00</Date>`.</span><span class="sxs-lookup"><span data-stu-id="cb24b-131">`<Date>2001-08-04T00:00:00</Date>`.</span></span>  
  
 <span data-ttu-id="cb24b-132">En el código siguiente se convierte un número entero en una cadena:</span><span class="sxs-lookup"><span data-stu-id="cb24b-132">The following code converts an integer to a string:</span></span>  
  
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
  
 <span data-ttu-id="cb24b-133">**Salida**</span><span class="sxs-lookup"><span data-stu-id="cb24b-133">**Output**</span></span>  
  
 `<Number>200</Number>`  
  
 <span data-ttu-id="cb24b-134">Pero si se convierte una cadena en un tipo **Boolean**, **Single** o **Double**, el tipo de .NET que se devuelve no es el mismo que el devuelto al usar la clase **System.Convert**.</span><span class="sxs-lookup"><span data-stu-id="cb24b-134">However, if you are converting a string to **Boolean**, **Single**, or **Double**, the .NET type that's returned is not the same as the type returned when using the **System.Convert** class.</span></span>  
  
## <a name="string-to-boolean"></a><span data-ttu-id="cb24b-135">Conversión de cadenas en Boolean</span><span class="sxs-lookup"><span data-stu-id="cb24b-135">String to Boolean</span></span>  
 <span data-ttu-id="cb24b-136">En la tabla siguiente se muestra qué tipo se genera para las cadenas de entrada dadas al convertir una cadena en **Boolean** mediante el método **ToBoolean**.</span><span class="sxs-lookup"><span data-stu-id="cb24b-136">The following table shows what type is generated for the given input strings, when converting a string to **Boolean** using the **ToBoolean** method.</span></span>  
  
|<span data-ttu-id="cb24b-137">Parámetro de entrada de cadena válido</span><span class="sxs-lookup"><span data-stu-id="cb24b-137">Valid string input parameter</span></span>|<span data-ttu-id="cb24b-138">Tipo de salida de .NET</span><span class="sxs-lookup"><span data-stu-id="cb24b-138">.NET output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="cb24b-139">"true"</span><span class="sxs-lookup"><span data-stu-id="cb24b-139">"true"</span></span>|<span data-ttu-id="cb24b-140">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="cb24b-140">Boolean.True</span></span>|  
|<span data-ttu-id="cb24b-141">"1"</span><span class="sxs-lookup"><span data-stu-id="cb24b-141">"1"</span></span>|<span data-ttu-id="cb24b-142">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="cb24b-142">Boolean.True</span></span>|  
|<span data-ttu-id="cb24b-143">"false"</span><span class="sxs-lookup"><span data-stu-id="cb24b-143">"false"</span></span>|<span data-ttu-id="cb24b-144">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="cb24b-144">Boolean.False</span></span>|  
|<span data-ttu-id="cb24b-145">"0"</span><span class="sxs-lookup"><span data-stu-id="cb24b-145">"0"</span></span>|<span data-ttu-id="cb24b-146">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="cb24b-146">Boolean.False</span></span>|  
  
 <span data-ttu-id="cb24b-147">Por ejemplo, dado el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="cb24b-147">For example, given the following XML:</span></span>  
  
 <span data-ttu-id="cb24b-148">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="cb24b-148">**Input**</span></span>  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>
```  
  
 <span data-ttu-id="cb24b-149">El código siguiente puede entender ambas líneas y **bvalue** es **System.Boolean.True**:</span><span class="sxs-lookup"><span data-stu-id="cb24b-149">Both can be understood by the following code, and **bvalue** is **System.Boolean.True**:</span></span>  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a><span data-ttu-id="cb24b-150">Conversión de cadenas en Single</span><span class="sxs-lookup"><span data-stu-id="cb24b-150">String to Single</span></span>  
 <span data-ttu-id="cb24b-151">En la tabla siguiente se muestra qué tipo se genera para las cadenas de entrada dadas, al convertir una cadena en **Single** mediante el método **ToSingle**.</span><span class="sxs-lookup"><span data-stu-id="cb24b-151">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToSingle** method.</span></span>  
  
|<span data-ttu-id="cb24b-152">Parámetro de entrada de cadena válido</span><span class="sxs-lookup"><span data-stu-id="cb24b-152">Valid string input parameter</span></span>|<span data-ttu-id="cb24b-153">Tipo de salida de .NET</span><span class="sxs-lookup"><span data-stu-id="cb24b-153">.NET output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="cb24b-154">"INF"</span><span class="sxs-lookup"><span data-stu-id="cb24b-154">"INF"</span></span>|<span data-ttu-id="cb24b-155">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="cb24b-155">Single.PositiveInfinity</span></span>|  
|<span data-ttu-id="cb24b-156">"-INF"</span><span class="sxs-lookup"><span data-stu-id="cb24b-156">"-INF"</span></span>|<span data-ttu-id="cb24b-157">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="cb24b-157">Single.NegativeInfinity</span></span>|  
  
## <a name="string-to-double"></a><span data-ttu-id="cb24b-158">Conversión de cadenas en Double</span><span class="sxs-lookup"><span data-stu-id="cb24b-158">String to Double</span></span>  
 <span data-ttu-id="cb24b-159">En la tabla siguiente se muestra qué tipo se genera para las cadenas de entrada dadas, al convertir una cadena en **Single** mediante el método **ToDouble**.</span><span class="sxs-lookup"><span data-stu-id="cb24b-159">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToDouble** method.</span></span>  
  
|<span data-ttu-id="cb24b-160">Parámetro de entrada de cadena válido</span><span class="sxs-lookup"><span data-stu-id="cb24b-160">Valid string input parameter</span></span>|<span data-ttu-id="cb24b-161">Tipo de salida de .NET</span><span class="sxs-lookup"><span data-stu-id="cb24b-161">.NET output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="cb24b-162">"INF"</span><span class="sxs-lookup"><span data-stu-id="cb24b-162">"INF"</span></span>|<span data-ttu-id="cb24b-163">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="cb24b-163">Double.PositiveInfinity</span></span>|  
|<span data-ttu-id="cb24b-164">"-INF"</span><span class="sxs-lookup"><span data-stu-id="cb24b-164">"-INF"</span></span>|<span data-ttu-id="cb24b-165">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="cb24b-165">Double.NegativeInfinity</span></span>|  
  
 <span data-ttu-id="cb24b-166">El código siguiente escribe `<Infinity>INF</Infinity>`:</span><span class="sxs-lookup"><span data-stu-id="cb24b-166">The following code writes `<Infinity>INF</Infinity>`:</span></span>  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb24b-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb24b-167">See also</span></span>

- [<span data-ttu-id="cb24b-168">Conversión de tipos de datos XML</span><span class="sxs-lookup"><span data-stu-id="cb24b-168">Conversion of XML Data Types</span></span>](conversion-of-xml-data-types.md)
- [<span data-ttu-id="cb24b-169">Conversión de tipos de .NET en cadenas</span><span class="sxs-lookup"><span data-stu-id="cb24b-169">Converting .NET Types to Strings</span></span>](converting-dotnet-types-to-strings.md)
