---
title: "Conversión de tipos de datos XML"
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
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d2f5f5d27b3d21ff12f5eea7613e80e73c5b6597
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="conversion-of-xml-data-types"></a><span data-ttu-id="57840-102">Conversión de tipos de datos XML</span><span class="sxs-lookup"><span data-stu-id="57840-102">Conversion of XML Data Types</span></span>
<span data-ttu-id="57840-103">La mayoría de los métodos que se encuentra en un **XmlConvert** clase se utilizan para convertir datos entre cadenas y formatos fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="57840-103">The majority of the methods found in an **XmlConvert** class are used to convert data between strings and strongly-typed formats.</span></span> <span data-ttu-id="57840-104">Los métodos son independientes de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="57840-104">Methods are locale independent.</span></span> <span data-ttu-id="57840-105">Esto significa que no la tienen en cuenta al realizar la conversión.</span><span class="sxs-lookup"><span data-stu-id="57840-105">This means that they do not take into account any locale settings when doing conversion.</span></span>  
  
## <a name="reading-string-as-types"></a><span data-ttu-id="57840-106">Leer cadenas como tipos</span><span class="sxs-lookup"><span data-stu-id="57840-106">Reading String as types</span></span>  
 <span data-ttu-id="57840-107">El ejemplo siguiente se lee una cadena y se convierte en una **DateTime** tipo.</span><span class="sxs-lookup"><span data-stu-id="57840-107">The following sample reads a string and converts it to a **DateTime** type.</span></span>  
  
 <span data-ttu-id="57840-108">Dada la siguiente entrada XML:</span><span class="sxs-lookup"><span data-stu-id="57840-108">Given the following XML input:</span></span>  
  
 <span data-ttu-id="57840-109">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="57840-109">**Input**</span></span>  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 <span data-ttu-id="57840-110">Este código convierte la cadena a la **DateTime** formato:</span><span class="sxs-lookup"><span data-stu-id="57840-110">This code converts the string to the **DateTime** format:</span></span>  
  
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
  
## <a name="writing-strings-as-types"></a><span data-ttu-id="57840-111">Escribir cadenas como tipos</span><span class="sxs-lookup"><span data-stu-id="57840-111">Writing Strings as types</span></span>  
 <span data-ttu-id="57840-112">El siguiente ejemplo se lee un **Int32** y lo convierte en una cadena.</span><span class="sxs-lookup"><span data-stu-id="57840-112">The following sample reads an **Int32** and converts it to a string.</span></span>  
  
 <span data-ttu-id="57840-113">Dada la siguiente entrada XML:</span><span class="sxs-lookup"><span data-stu-id="57840-113">Given the following XML input:</span></span>  
  
 <span data-ttu-id="57840-114">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="57840-114">**Input**</span></span>  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 <span data-ttu-id="57840-115">Este código convierte el **Int32** en un **cadena**:</span><span class="sxs-lookup"><span data-stu-id="57840-115">This code converts the **Int32** into a **String**:</span></span>  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a><span data-ttu-id="57840-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="57840-116">See Also</span></span>  
 [<span data-ttu-id="57840-117">Convertir cadenas en tipos de datos de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="57840-117">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [<span data-ttu-id="57840-118">Convertir tipos de .NET Framework en cadenas</span><span class="sxs-lookup"><span data-stu-id="57840-118">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
