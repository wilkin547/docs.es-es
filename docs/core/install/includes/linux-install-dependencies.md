---
ms.openlocfilehash: b371525c9f4e57c6a09e5bb9232884e5c5e707e0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602769"
---

Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente. Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:

- lttng-ust
- libcurl
- openssl-libs
- krb5-libs
- libicu
- zlib
- libunwind
- libuuid

Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.

Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:

- [libgdiplus (versión 6.0.1 o posterior)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema. Para obtener más información, vea <https://www.mono-project.com/download/stable/>.
