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
ms.openlocfilehash: a1fbbb8415e5e3405f039489aa071b0624065a9d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530148"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="2c19a-102">-preferreduilang (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="2c19a-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="2c19a-103">Mediante la opción del compilador `-preferreduilang`, puede especificar el idioma en el que el compilador de C# muestra el resultado, como los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="2c19a-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c19a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c19a-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="2c19a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2c19a-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="2c19a-106">El [nombre del idioma](/windows/desktop/Intl/language-names) del idioma que se va a usar para los resultados del compilador.</span><span class="sxs-lookup"><span data-stu-id="2c19a-106">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c19a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c19a-107">Remarks</span></span>  
 <span data-ttu-id="2c19a-108">Puede usar la opción del compilador `-preferreduilang` para especificar el idioma que quiere que use el compilador de C# para los mensajes de error y otros resultados de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="2c19a-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="2c19a-109">Si el paquete de idioma para el idioma no está instalado, se usa la configuración del idioma del sistema operativo en su lugar, y no se notifica ningún error.</span><span class="sxs-lookup"><span data-stu-id="2c19a-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="2c19a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c19a-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c19a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c19a-111">See Also</span></span>

- [<span data-ttu-id="2c19a-112">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="2c19a-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
