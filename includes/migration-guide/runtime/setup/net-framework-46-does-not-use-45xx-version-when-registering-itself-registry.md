---
ms.openlocfilehash: 08c16f261338148619de2e484c73046b9d9a6bfe
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858491"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="ed04e-101">En .NET Framework 4.6 no se usa una versión de 4.5.x.x al registrarse a sí mismo en el Registro</span><span class="sxs-lookup"><span data-stu-id="ed04e-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ed04e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ed04e-102">Details</span></span>|<span data-ttu-id="ed04e-103">Como se podría esperar, la clave de versión que se establece en el Registro (en <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) para .NET Framework 4.6 comienza con "4.6", no con "4.5".</span><span class="sxs-lookup"><span data-stu-id="ed04e-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="ed04e-104">Las aplicaciones que dependen de estas claves del Registro para saber qué versiones de .NET Framework están instaladas en un equipo se deben actualizar para entender que 4.6 es una nueva versión posible, y que es compatible con las versiones 4.5.x anteriores.</span><span class="sxs-lookup"><span data-stu-id="ed04e-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>|
|<span data-ttu-id="ed04e-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ed04e-105">Suggestion</span></span>|<span data-ttu-id="ed04e-106">Actualice las aplicaciones que sondean una instalación de .NET Framework 4.5 examinando las claves del Registro de 4.5 para que también acepten la versión 4.6.</span><span class="sxs-lookup"><span data-stu-id="ed04e-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>|
|<span data-ttu-id="ed04e-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ed04e-107">Scope</span></span>|<span data-ttu-id="ed04e-108">Borde</span><span class="sxs-lookup"><span data-stu-id="ed04e-108">Edge</span></span>|
|<span data-ttu-id="ed04e-109">Versión</span><span class="sxs-lookup"><span data-stu-id="ed04e-109">Version</span></span>|<span data-ttu-id="ed04e-110">4.6</span><span class="sxs-lookup"><span data-stu-id="ed04e-110">4.6</span></span>|
|<span data-ttu-id="ed04e-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="ed04e-111">Type</span></span>|<span data-ttu-id="ed04e-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ed04e-112">Runtime</span></span>|

