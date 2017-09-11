---
title: "Cómo: Convertir entre codificaciones heredadas y Unicode (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], legacy to unicode encoding
- strings [C#], converting between encodings
ms.assetid: 4eed7d8e-47ab-4a7c-8b95-9645a0ef000b
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a016f4ab7de25eec408243cb9b467f9255556bba
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-between-legacy-encodings-and-unicode-c-programming-guide"></a><span data-ttu-id="56f03-102">Cómo: Convertir entre codificaciones heredadas y Unicode (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="56f03-102">How to: Convert Between Legacy Encodings and Unicode (C# Programming Guide)</span></span>
<span data-ttu-id="56f03-103">En C#, todas las cadenas de la memoria se codifican como Unicode (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="56f03-103">In C#, all strings in memory are encoded as Unicode (UTF-16).</span></span> <span data-ttu-id="56f03-104">Cuando pase los datos del almacenamiento a un objeto `string`, los datos se convierten automáticamente en UTF-16.</span><span class="sxs-lookup"><span data-stu-id="56f03-104">When you bring data from storage into a `string` object, the data is automatically converted to UTF-16.</span></span> <span data-ttu-id="56f03-105">Si los datos contienen solo valores ASCII desde 0 a 127, la conversión no necesita ninguna acción adicional por su parte.</span><span class="sxs-lookup"><span data-stu-id="56f03-105">If the data contains only ASCII values from 0 through 127, the conversion requires no extra effort on your part.</span></span> <span data-ttu-id="56f03-106">En cambio, si el texto de origen contiene valores de byte ASCII extendidos (de 128 a 255), los caracteres extendidos se interpretarán de manera predeterminada según la página de código actual.</span><span class="sxs-lookup"><span data-stu-id="56f03-106">However, if the source text contains extended ASCII byte values (128 through 255), the extended characters will be interpreted by default according to the current code page.</span></span> <span data-ttu-id="56f03-107">Para especificar que el texto de origen debe interpretarse según una página de código diferente, use la clase <xref:System.Text.Encoding?displayProperty=fullName> como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="56f03-107">To specify that the source text should be interpreted according to a different code page, use the <xref:System.Text.Encoding?displayProperty=fullName> class as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56f03-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56f03-108">Example</span></span>  
 <span data-ttu-id="56f03-109">En el ejemplo siguiente se muestra cómo convertir un archivo de texto que se ha codificado en ASCII de 8 bits, interpretando el texto de origen según la página de códigos de Windows 737.</span><span class="sxs-lookup"><span data-stu-id="56f03-109">The following example shows how to convert a text file that has been encoded in 8-bit ASCII, interpreting the source text according to Windows Code Page 737.</span></span>  
  
 <span data-ttu-id="56f03-110">[!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="56f03-110">[!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f03-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="56f03-111">See Also</span></span>  
 [<span data-ttu-id="56f03-112">Cadenas</span><span class="sxs-lookup"><span data-stu-id="56f03-112">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

