---
ms.openlocfilehash: b371525c9f4e57c6a09e5bb9232884e5c5e707e0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602769"
---

<span data-ttu-id="54af0-101">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="54af0-101">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="54af0-102">Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="54af0-102">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="54af0-103">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="54af0-103">lttng-ust</span></span>
- <span data-ttu-id="54af0-104">libcurl</span><span class="sxs-lookup"><span data-stu-id="54af0-104">libcurl</span></span>
- <span data-ttu-id="54af0-105">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="54af0-105">openssl-libs</span></span>
- <span data-ttu-id="54af0-106">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="54af0-106">krb5-libs</span></span>
- <span data-ttu-id="54af0-107">libicu</span><span class="sxs-lookup"><span data-stu-id="54af0-107">libicu</span></span>
- <span data-ttu-id="54af0-108">zlib</span><span class="sxs-lookup"><span data-stu-id="54af0-108">zlib</span></span>
- <span data-ttu-id="54af0-109">libunwind</span><span class="sxs-lookup"><span data-stu-id="54af0-109">libunwind</span></span>
- <span data-ttu-id="54af0-110">libuuid</span><span class="sxs-lookup"><span data-stu-id="54af0-110">libuuid</span></span>

<span data-ttu-id="54af0-111">Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="54af0-111">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="54af0-112">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="54af0-112">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="54af0-113">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="54af0-113">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="54af0-114">libgdiplus (versión 6.0.1 o posterior)</span><span class="sxs-lookup"><span data-stu-id="54af0-114">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="54af0-115">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="54af0-115">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="54af0-116">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="54af0-116">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>
