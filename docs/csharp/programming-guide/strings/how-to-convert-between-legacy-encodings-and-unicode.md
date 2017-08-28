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
# <a name="how-to-convert-between-legacy-encodings-and-unicode-c-programming-guide"></a>Cómo: Convertir entre codificaciones heredadas y Unicode (Guía de programación de C#)
En C#, todas las cadenas de la memoria se codifican como Unicode (UTF-16). Cuando pase los datos del almacenamiento a un objeto `string`, los datos se convierten automáticamente en UTF-16. Si los datos contienen solo valores ASCII desde 0 a 127, la conversión no necesita ninguna acción adicional por su parte. En cambio, si el texto de origen contiene valores de byte ASCII extendidos (de 128 a 255), los caracteres extendidos se interpretarán de manera predeterminada según la página de código actual. Para especificar que el texto de origen debe interpretarse según una página de código diferente, use la clase <xref:System.Text.Encoding?displayProperty=fullName> como se muestra en el ejemplo siguiente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo convertir un archivo de texto que se ha codificado en ASCII de 8 bits, interpretando el texto de origen según la página de códigos de Windows 737.  
  
 [!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Cadenas](../../../csharp/programming-guide/strings/index.md)

