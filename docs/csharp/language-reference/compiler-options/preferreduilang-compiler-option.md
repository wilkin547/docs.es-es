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
ms.openlocfilehash: 7ebafcf446c9033c93e0c5fa5e11ea2930bd2e1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602558"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="05128-102">-preferreduilang (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="05128-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="05128-103">Mediante la opción del compilador `-preferreduilang`, puede especificar el idioma en el que el compilador de C# muestra el resultado, como los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="05128-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05128-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05128-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="05128-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="05128-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="05128-106">El [nombre del idioma](/windows/desktop/Intl/language-names) del idioma que se va a usar para los resultados del compilador.</span><span class="sxs-lookup"><span data-stu-id="05128-106">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05128-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="05128-107">Remarks</span></span>  
 <span data-ttu-id="05128-108">Puede usar la opción del compilador `-preferreduilang` para especificar el idioma que quiere que use el compilador de C# para los mensajes de error y otros resultados de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="05128-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="05128-109">Si el paquete de idioma para el idioma no está instalado, se usa la configuración del idioma del sistema operativo en su lugar, y no se notifica ningún error.</span><span class="sxs-lookup"><span data-stu-id="05128-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="05128-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05128-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05128-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="05128-111">See also</span></span>

- [<span data-ttu-id="05128-112">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="05128-112">C# Compiler Options</span></span>](./index.md)
