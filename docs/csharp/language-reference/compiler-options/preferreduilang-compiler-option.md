---
title: -preferreduilang (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: d079441e91ff90bcc974564bbd7069e0548a7d77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575302"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="92887-102">-preferreduilang (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="92887-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="92887-103">Mediante la opción del compilador `-preferreduilang`, puede especificar el idioma en el que el compilador de C# muestra el resultado, como los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="92887-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92887-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92887-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="92887-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="92887-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="92887-106">El [nombre del idioma](/windows/desktop/Intl/language-names) del idioma que se va a usar para los resultados del compilador.</span><span class="sxs-lookup"><span data-stu-id="92887-106">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92887-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92887-107">Remarks</span></span>  
 <span data-ttu-id="92887-108">Puede usar la opción del compilador `-preferreduilang` para especificar el idioma que quiere que use el compilador de C# para los mensajes de error y otros resultados de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="92887-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="92887-109">Si el paquete de idioma para el idioma no está instalado, se usa la configuración del idioma del sistema operativo en su lugar, y no se notifica ningún error.</span><span class="sxs-lookup"><span data-stu-id="92887-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="92887-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92887-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92887-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="92887-111">See also</span></span>

- [<span data-ttu-id="92887-112">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="92887-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
