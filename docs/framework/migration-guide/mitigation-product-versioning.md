---
title: 'Mitigación: Control de versiones de producto'
description: En este artículo, aprenderá cómo ha cambiado .NET Framework 4.6 y versiones posteriores del producto con respecto a las versiones anteriores.
ms.date: 03/30/2017
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
ms.openlocfilehash: 442c06446e763758d3a150ee9ff884a616541c07
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475403"
---
# <a name="mitigation-product-versioning"></a>Mitigación: control de versiones de producto

En .NET Framework 4.6 y versiones posteriores, el control de versiones del producto ha cambiado con respecto a las versiones anteriores de .NET Framework (.NET Framework 4, 4.5, 4.5.1 y 4.5.2).

## <a name="product-versioning-changes"></a>Cambios en el control de versiones de producto

Estos son los cambios detallados:

- El valor de la entrada `Version` en la clave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` ha cambiado a `4.6.`*xxxxx* para .NET Framework 4.6 y versiones secundarias, y a `4.7.`*xxxxx* para .NET Framework 4.7. En .NET Framework 4.5, 4.5.1 y 4.5.2, tenía el formato `4.5.`*xxxxx*.

- El control de versiones de producto y archivo para los archivos de .NET Framework ha cambiado desde el esquema de control de versiones anterior de `4.0.30319.x` a `4.6.X.0` para .NET Framework 4.6 y las versiones secundarias, y a `4.7.X.0` para .NET Framework 4.7 y las versiones secundarias. Puede consultar estos nuevos valores al ver las **Propiedades** del archivo después de haber hecho clic con el botón derecho en un archivo.

- Los atributos <xref:System.Reflection.AssemblyFileVersionAttribute> y <xref:System.Reflection.AssemblyInformationalVersionAttribute> de ensamblados administrados tienen valores <xref:System.Version> con la forma `4.6.X.0` para .NET Framework 4.6 y sus versiones puntuales, y `4.7.X.0` para .NET Framework 4.7.

- A partir de .NET Framework 4.6, la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> devuelve la cadena de versión no editable `4.0.30319.42000`. En .NET Framework 4, 4.5, 4.5.1 y 4.5.2, devuelve cadenas de versión con el formato `4.0.30319.xxxxx`, donde `xxxxx` es inferior a 42000 (por ejemplo, "4.0.30319.18010"). Tenga en cuenta que no se recomienda que el código de la aplicación tome nuevas dependencias en la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType>.

### <a name="handling-the-product-versioning-changes"></a>Administrar los cambios en el control de versiones de producto

En general, las aplicaciones deben depender de las técnicas recomendadas para detectar elementos como la versión del tiempo de ejecución de .NET Framework y el directorio de instalación:

- Para detectar la versión de tiempo de ejecución de .NET Framework, vea [Cómo: Determinar qué versiones de .NET Framework están instaladas](how-to-determine-which-versions-are-installed.md).

- Para determinar la ruta de instalación de .NET Framework, utilice el valor de la entrada `InstallPath` en la clave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`.

  > [!IMPORTANT]
  > El nombre de la subclave es `NET Framework Setup`, no `.NET Framework Setup`.

- Para determinar la ruta de acceso de directorio a Common Language Runtime de .NET Framework, llame al método <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType>.

- Para obtener la versión de CLR, llame al método <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType>.   Para .NET Framework 4 y sus versiones secundarias (.NET Framework 4.5, 4.5.1, 4.5.2 y .NET Framework 4.6, 4.6.1, 4.6.2 y 4.7), devuelve la cadena `v4.0.30319`.

## <a name="see-also"></a>Vea también

- [Compatibilidad de aplicaciones](application-compatibility.md)
