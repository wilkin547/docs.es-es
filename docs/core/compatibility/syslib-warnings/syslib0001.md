---
title: Advertencia SYSLIB0001
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0001.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 6c4b6a2f41e9dc044ef76bb5a53a4a54a44bca5a
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596415"
---
# <a name="syslib0001-the-utf-7-encoding-is-insecure"></a><span data-ttu-id="08aac-103">SYSLIB0001: la codificación UTF-7 no es segura</span><span class="sxs-lookup"><span data-stu-id="08aac-103">SYSLIB0001: The UTF-7 encoding is insecure</span></span>

<span data-ttu-id="08aac-104">La codificación UTF-7 ya no se usa de forma generalizada en la mayoría de las aplicaciones, y muchas especificaciones ahora [prohíben su uso](https://security.stackexchange.com/a/68609/3573) en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="08aac-104">The UTF-7 encoding is no longer in wide use among applications, and many specs now [forbid its use](https://security.stackexchange.com/a/68609/3573) in interchange.</span></span> <span data-ttu-id="08aac-105">En ocasiones, también se [usa como vector de ataque](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7) en aplicaciones que no anticipan el encuentro de datos codificados en UTF-7.</span><span class="sxs-lookup"><span data-stu-id="08aac-105">It's also occasionally [used as an attack vector](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7) in applications that don't anticipate encountering UTF-7-encoded data.</span></span> <span data-ttu-id="08aac-106">Microsoft advierte contra el uso de <xref:System.Text.UTF7Encoding?displayProperty=nameWithType>, porque no proporciona detección de errores.</span><span class="sxs-lookup"><span data-stu-id="08aac-106">Microsoft warns against use of <xref:System.Text.UTF7Encoding?displayProperty=nameWithType> because it doesn't provide error detection.</span></span>

<span data-ttu-id="08aac-107">Por tanto, las siguientes API se han marcado como obsoletas a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="08aac-107">Consequently, the following APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="08aac-108">El uso de estas API genera una advertencia `SYSLIB0001` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="08aac-108">Use of these APIs generates warning `SYSLIB0001` at compile time.</span></span>

- <span data-ttu-id="08aac-109">Propiedad<xref:System.Text.Encoding.UTF7?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="08aac-109"><xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> property</span></span>
- <span data-ttu-id="08aac-110">Constructores <xref:System.Text.UTF7Encoding.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="08aac-110"><xref:System.Text.UTF7Encoding.%23ctor%2A> constructors</span></span>

## <a name="workarounds"></a><span data-ttu-id="08aac-111">Soluciones alternativas</span><span class="sxs-lookup"><span data-stu-id="08aac-111">Workarounds</span></span>

- <span data-ttu-id="08aac-112">Si usa <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> o <xref:System.Text.UTF7Encoding> en su propio protocolo o formato de archivo:</span><span class="sxs-lookup"><span data-stu-id="08aac-112">If you're using <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> or <xref:System.Text.UTF7Encoding> within your own protocol or file format:</span></span>

  <span data-ttu-id="08aac-113">Cambie al uso de <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> o <xref:System.Text.UTF8Encoding>.</span><span class="sxs-lookup"><span data-stu-id="08aac-113">Switch to using <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> or <xref:System.Text.UTF8Encoding>.</span></span> <span data-ttu-id="08aac-114">UTF-8 es un estándar del sector y es compatible con numerosos lenguajes, sistemas operativos y entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="08aac-114">UTF-8 is an industry standard and is widely supported across languages, operating systems, and runtimes.</span></span> <span data-ttu-id="08aac-115">El uso de UTF-8 facilita el mantenimiento futuro del código y hace que sea más interoperable con el resto del ecosistema.</span><span class="sxs-lookup"><span data-stu-id="08aac-115">Using UTF-8 eases future maintenance of your code and makes it more interoperable with the rest of the ecosystem.</span></span>

- <span data-ttu-id="08aac-116">Si va a comparar una instancia de <xref:System.Text.Encoding> con <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="08aac-116">If you're comparing an <xref:System.Text.Encoding> instance against <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>:</span></span>

  <span data-ttu-id="08aac-117">Considere mejor la posibilidad de realizar una comprobación con la página de códigos UTF-7 conocidos, que es `65000`.</span><span class="sxs-lookup"><span data-stu-id="08aac-117">Instead, consider performing a check against the well-known UTF-7 code page, which is `65000`.</span></span> <span data-ttu-id="08aac-118">De esta manera, evita la advertencia y también se controlan algunos casos extremos, como, por ejemplo, si alguien llamó a `new UTF7Encoding()` o incluyó el tipo en una subclase.</span><span class="sxs-lookup"><span data-stu-id="08aac-118">By comparing against the code page, you avoid the warning and also handle some edge cases, such as if somebody called `new UTF7Encoding()` or subclassed the type.</span></span>

  ```csharp
  void DoSomething(Encoding enc)
  {
      // Don't perform the check this way.
      // It produces a warning and misses some edge cases.
      if (enc == Encoding.UTF7)
      {
          // Encoding is UTF-7.
      }

      // Instead, perform the check this way.
      if (enc != null && enc.CodePage == 65000)
      {
          // Encoding is UTF-7.
      }
  }
  ```

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="08aac-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="08aac-119">See also</span></span>

- [<span data-ttu-id="08aac-120">Las rutas de acceso al código UTF-7 están obsoletas</span><span class="sxs-lookup"><span data-stu-id="08aac-120">UTF-7 code paths are obsolete</span></span>](../core-libraries/5.0/utf-7-code-paths-obsolete.md)
