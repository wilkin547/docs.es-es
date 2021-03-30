---
ms.openlocfilehash: e3f6d2d4af55e831a262a2211bf495e2f2bd772e
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104879781"
---

Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente. Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:

- krb5-libs
- libicu
- openssl-libs
- zlib

Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.

Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/main/Documentation/self-contained-linux-apps.md).

En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:

- [libgdiplus (versión 6.0.1 o posterior)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema. Para obtener más información, vea <https://www.mono-project.com/download/stable/>.
