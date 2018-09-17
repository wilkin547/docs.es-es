---
title: Conversión de tipos de datos XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cec2b85c55871c8a21a74e79cfcdd041fa063bec
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45664584"
---
# <a name="conversion-of-xml-data-types"></a><span data-ttu-id="18271-102">Conversión de tipos de datos XML</span><span class="sxs-lookup"><span data-stu-id="18271-102">Conversion of XML Data Types</span></span>
<span data-ttu-id="18271-103">La mayor parte de los métodos que se encuentran en una clase **XmlConvert** se utilizan para convertir datos entre cadenas y formatos fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="18271-103">The majority of the methods found in an **XmlConvert** class are used to convert data between strings and strongly-typed formats.</span></span> <span data-ttu-id="18271-104">Los métodos son independientes de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="18271-104">Methods are locale independent.</span></span> <span data-ttu-id="18271-105">Esto significa que no la tienen en cuenta al realizar la conversión.</span><span class="sxs-lookup"><span data-stu-id="18271-105">This means that they do not take into account any locale settings when doing conversion.</span></span>  
  
## <a name="reading-string-as-types"></a><span data-ttu-id="18271-106">Leer cadenas como tipos</span><span class="sxs-lookup"><span data-stu-id="18271-106">Reading String as types</span></span>  
 <span data-ttu-id="18271-107">En el ejemplo siguiente se lee una cadena y se convierte en un tipo **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="18271-107">The following sample reads a string and converts it to a **DateTime** type.</span></span>  
  
 <span data-ttu-id="18271-108">Dada la siguiente entrada XML:</span><span class="sxs-lookup"><span data-stu-id="18271-108">Given the following XML input:</span></span>  
  
 <span data-ttu-id="18271-109">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="18271-109">**Input**</span></span>  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 <span data-ttu-id="18271-110">Este código convierte la cadena al formato **DateTime**:</span><span class="sxs-lookup"><span data-stu-id="18271-110">This code converts the string to the **DateTime** format:</span></span>  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a><span data-ttu-id="18271-111">Escribir cadenas como tipos</span><span class="sxs-lookup"><span data-stu-id="18271-111">Writing Strings as types</span></span>  
 <span data-ttu-id="18271-112">En el ejemplo siguiente se lee un valor **Int32** y se convierte en una cadena.</span><span class="sxs-lookup"><span data-stu-id="18271-112">The following sample reads an **Int32** and converts it to a string.</span></span>  
  
 <span data-ttu-id="18271-113">Dada la siguiente entrada XML:</span><span class="sxs-lookup"><span data-stu-id="18271-113">Given the following XML input:</span></span>  
  
 <span data-ttu-id="18271-114">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="18271-114">**Input**</span></span>  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 <span data-ttu-id="18271-115">Este código convierte el valor **Int32** en **String**:</span><span class="sxs-lookup"><span data-stu-id="18271-115">This code converts the **Int32** into a **String**:</span></span>  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a><span data-ttu-id="18271-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="18271-116">See also</span></span>

- [<span data-ttu-id="18271-117">Conversión de cadenas en tipos de datos de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="18271-117">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
- [<span data-ttu-id="18271-118">Conversión de tipos de .NET Framework en cadenas</span><span class="sxs-lookup"><span data-stu-id="18271-118">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
