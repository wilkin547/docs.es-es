---
title: Revisión de adaptabilidad
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- world-ready applications, localizability
- application development [.NET Framework], localization
- localizability [.NET Framework]
- international applications [.NET Framework], localizability
- globalization [.NET Framework], localizability
- culture, localizability
- localization [.NET Framework], localizability
- global applications, localizability
- localizing resources
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
ms.openlocfilehash: ef23cff2416792f13fda04dbe9beb34cbacfd7ea
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288282"
---
# <a name="localizability-review"></a>Revisión de localizabilidad

La revisión de localización es un paso intermedio en el desarrollo de una aplicación de uso internacional. Comprueba que una aplicación globalizada está preparada para la localización e identifica cualquier código o los aspectos de la interfaz de usuario que requieren un tratamiento especial. Este paso también ayuda a asegurarse de que el proceso de localización no introducirá defectos funcionales en la aplicación. Una vez solucionados todos los problemas que planteó la revisión de localización, la aplicación estará lista para la localización. Si la revisión de localización es exhaustiva, no tiene que modificar ningún código fuente durante el proceso de localización.

La revisión de localización consta de las tres comprobaciones siguientes:

- [¿Se han implementado las recomendaciones de globalización?](#global)

- [¿Las características que tienen en cuenta las referencias culturales se han controlado correctamente?](#culture)

- [¿Ha probado la aplicación con datos internacionales?](#test)

<a name="global"></a>
## <a name="implement-globalization-recommendations"></a>Implementación de recomendaciones de globalización

Si ha diseñado y desarrollado la aplicación con la localización en mente y, además, si ha seguido las recomendaciones indicadas en el artículo [Globalización](globalization.md), la revisión de localización, en gran medida, será un paso para el control de calidad. Sin embargo, durante esta fase, debe revisar e implementar las recomendaciones de [globalización](globalization.md) y corregir los errores del código fuente que impiden la localización.

<a name="culture"></a>
## <a name="handle-culture-sensitive-features"></a>Control de características que tienen en cuenta la referencia cultural

.NET no proporciona soporte técnico de programación en un número de áreas que varían enormemente según la referencia cultural. En la mayoría de los casos, tendrá que escribir código personalizado para controlar áreas de características como las siguientes:

- Direcciones

- Números de teléfono

- Tamaños de papel

- Unidades de medida usadas para longitud, peso, área, volumen y temperatura

   Aunque .NET no ofrece compatibilidad integrada para la conversión entre unidades de medida, puede utilizar la propiedad <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> para determinar si un determinado país o región utiliza el sistema métrico, como se muestra en el ejemplo siguiente.

   [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
   [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]

<a name="test"></a>
## <a name="test-your-application"></a>Probar la aplicación

Para localizar la aplicación, debe probarla mediante el uso de datos internacionales en versiones internacionales del sistema operativo. Aunque la mayor parte de la interfaz de usuario no se localizará en este momento, podrá detectar problemas como los siguientes:

- Datos serializados que no se deserializan correctamente en las versiones del sistema operativo.

- Datos numéricos que no reflejan las convenciones de la referencia cultural actual. Por ejemplo, pueden mostrarse números con separadores de grupos, separadores decimales o símbolos de moneda inexactos.

- Los datos de fecha y hora no reflejan las convenciones de la referencia cultural actual. Por ejemplo, los números que representan el mes y día pueden aparecer en el orden equivocado, los separadores de fecha pueden ser incorrectos o la información de zona horaria puede ser incorrecta.

- Los recursos que no se pueden encontrar porque no se ha identificado una referencia cultural predeterminada para la aplicación.

- Las cadenas que se muestran en un orden inusual para la referencia cultural específica.

- Las comparaciones de cadenas o las comparaciones de igualdad que devuelven resultados inesperados.

Si ha seguido las recomendaciones de globalización al desarrollar la aplicación, ha controlado correctamente las características que tienen en cuenta la referencia cultural y ha identificado y solucionado los problemas de localización planteados durante las pruebas, puede continuar con el paso siguiente, [Localización](localization.md).

## <a name="see-also"></a>Vea también

- [Globalización y localización](index.md)
- [Localización](localization.md)
- [Globalización](globalization.md)
- [Recursos de aplicaciones de escritorio](../../framework/resources/index.md)
