---
title: Archivos de configuración predefinidos (análisis de código)
description: Obtenga información sobre el uso de editorconfig y los archivos de conjunto de reglas predefinidos para tener como destino tipos específicos de análisis de código.
ms.date: 09/24/2020
ms.topic: conceptual
ms.openlocfilehash: 4937dcab1183fa3f63be4afc71627a7c7c08c6bd
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "96594372"
---
# <a name="predefined-configuration-files"></a>Archivos de configuración predefinidos

Los archivos de [conjunto de reglas](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) y EditorConfig predefinidos están disponibles para facilitar y agilizar la habilitación de una categoría de reglas de calidad de código, como reglas de seguridad o de diseño. Al habilitar una categoría específica de reglas, puede identificar problemas de destino y condiciones específicas. Para tener acceso a estos archivos predefinidos, instale el paquete del analizador de NuGet [Microsoft. CodeAnalysis. NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) .

[Microsoft. CodeAnalysis. NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) incluye archivos EditorConfig y conjuntos de reglas predefinidos para las siguientes categorías de reglas:

- Todas las reglas
- Flujo de datos
- Diseño
- Documentación
- Globalización
- Interoperabilidad
- Capacidad de mantenimiento
- Nomenclatura
- Rendimiento
- Trasladado desde FxCop
- Confiabilidad
- Seguridad
- Uso

Cada una de esas categorías de reglas tiene un EditorConfig o un archivo de conjunto de reglas para:

- Habilitar todas las reglas de la categoría (y deshabilitar todas las demás reglas)
- Usar la gravedad predeterminada de cada regla y habilitarla de forma predeterminada (y deshabilitar todas las demás reglas)

> [!TIP]
> La categoría "todas las reglas" tiene un EditorConfig adicional o un archivo de conjunto de reglas para deshabilitar todas las reglas. Use este archivo para deshacerse rápidamente de cualquier error o advertencia del analizador en un proyecto.

## <a name="predefined-editorconfig-files"></a>Archivos EditorConfig predefinidos

Los archivos EditorConfig predefinidos para el paquete Microsoft. CodeAnalysis. NetAnalyzers Analyzer se encuentran en el subdirectorio *EditorConfig* de donde se instaló el paquete NuGet. Por ejemplo, el archivo EditorConfig para habilitar todas las reglas de seguridad se encuentra en *EditorConfig/SecurityRulesEnabled/. EditorConfig*.

Copie el archivo *. editorconfig* elegido en el directorio raíz del proyecto.

## <a name="predefined-rule-sets"></a>Conjunto de reglas predefinidas

Los archivos de conjunto de reglas predefinidos para el paquete Microsoft. CodeAnalysis. NetAnalyzers Analyzer se encuentran en el subdirectorio de *conjuntos* de reglas donde se instaló el paquete NuGet. Por ejemplo, el archivo de conjunto de reglas para habilitar todas las reglas de seguridad se encuentra en conjuntos de reglas */SecurityRulesEnabled. ruleset*. Copie uno o más conjuntos de reglas y péguelos en el directorio que contiene el proyecto.

## <a name="see-also"></a>Vea también

- [Configuración del analizador](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [Opciones de regla de estilo de código .NET para EditorConfig](code-style-rule-options.md)
