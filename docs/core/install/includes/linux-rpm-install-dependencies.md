---
ms.openlocfilehash: 3d8179c5c0e84f8ff1197cce7790c80a5f5a4f6d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619459"
---

<span data-ttu-id="23636-101">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="23636-101">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="23636-102">Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="23636-102">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="23636-103">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="23636-103">krb5-libs</span></span>
- <span data-ttu-id="23636-104">libicu</span><span class="sxs-lookup"><span data-stu-id="23636-104">libicu</span></span>
- <span data-ttu-id="23636-105">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="23636-105">openssl-libs</span></span>

<span data-ttu-id="23636-106">Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="23636-106">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="23636-107">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="23636-107">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="23636-108">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="23636-108">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="23636-109">libgdiplus (versión 6.0.1 o posterior)</span><span class="sxs-lookup"><span data-stu-id="23636-109">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="23636-110">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="23636-110">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="23636-111">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="23636-111">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>
