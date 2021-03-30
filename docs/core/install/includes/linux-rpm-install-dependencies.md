---
ms.openlocfilehash: e3f6d2d4af55e831a262a2211bf495e2f2bd772e
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104879781"
---

<span data-ttu-id="49789-101">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="49789-101">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="49789-102">Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="49789-102">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="49789-103">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="49789-103">krb5-libs</span></span>
- <span data-ttu-id="49789-104">libicu</span><span class="sxs-lookup"><span data-stu-id="49789-104">libicu</span></span>
- <span data-ttu-id="49789-105">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="49789-105">openssl-libs</span></span>
- <span data-ttu-id="49789-106">zlib</span><span class="sxs-lookup"><span data-stu-id="49789-106">zlib</span></span>

<span data-ttu-id="49789-107">Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="49789-107">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="49789-108">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/main/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="49789-108">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/main/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="49789-109">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="49789-109">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="49789-110">libgdiplus (versión 6.0.1 o posterior)</span><span class="sxs-lookup"><span data-stu-id="49789-110">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="49789-111">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="49789-111">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="49789-112">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="49789-112">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>
