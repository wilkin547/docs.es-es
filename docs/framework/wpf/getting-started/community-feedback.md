---
title: Recursos de la comunidad
ms.date: 03/01/2018
helpviewer_keywords:
- community resources [WPF]
- forums [WPF]
- bug descriptions [WPF]
ms.assetid: 468b060a-d54b-4900-a74a-9faccb554045
ms.openlocfilehash: 0bb94626d4e97f55c89bf239fc298b6bce8fd870
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124681"
---
# <a name="wpf-community-feedback"></a>Comentarios de la comunidad de WPF

Microsoft ofrece una amplia variedad de recursos de la comunidad para que pueda obtener información acerca de los Windows Presentation Foundation (WPF) y proporcionar comentarios sobre ellos. Estos recursos incluyen foros y el sitio de la [comunidad de desarrolladores de Visual Studio](https://developercommunity.visualstudio.com/) . Cada recurso de comunidad proporciona un conjunto diferente de ventajas. Estas ventajas se describen aquí, así como un conjunto de prácticas recomendadas para usar cada una de ellas para garantizar la mejor respuesta de la comunidad en gran medida y en Microsoft en particular.

> [!NOTE]
> No utilice la sección de comentarios que se encuentra en la parte inferior de cada página para enviar comentarios sobre el producto. Estos vínculos son solo para comentarios sobre la documentación.

## <a name="forums"></a>Foros

El [Foro de WPF](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=wpf) es el recurso de la comunidad principal para tratar y resolver problemas. Los foros facilitan el debate y la resolución de problemas al ofrecer un conjunto completo de características de compatibilidad que incluyen:

- Búsqueda.
- Seguimiento de debates.
- Formato enriquecido para texto y código.
- Integración de Visual Studio.
- Implicación de los profesionales más valiosos (MVP) y de la comunidad.
- Supervisión para asegurarse de que las publicaciones se responden en el menor tiempo posible.

Otra opción para hacer preguntas a la comunidad sobre WPF es [Stack Overflow](https://stackoverflow.com/questions/tagged/wpf).

### <a name="forum-best-practices"></a>Prácticas recomendadas del Foro

El uso de los procedimientos recomendados siguientes ayuda a solucionar los problemas publicados en el foro de WPF en el tiempo más rápido posible. Estos procedimientos se aplican a todos los foros.

#### <a name="search-existing-posts"></a>Buscar publicaciones existentes

Algunos problemas se producen con tanta frecuencia que otras personas ya se han enfrentado antes a ellos. Por consiguiente, puede resolver el problema rápidamente, o puede agregar su entrada a una discusión existente.

#### <a name="use-meaningful-titles"></a>Usar títulos significativos

Los títulos concisos y significativos mejoran la detectabilidad de las publicaciones. También facilitan que otros miembros de la comunidad del Foro de WPF determinen si pueden resolver el problema.

#### <a name="include-appropriate-content"></a>Incluir el contenido adecuado

Describa el problema y cómo ha intentado trabajar con él. Si es posible, incluya fragmentos de código adicionales o el ejemplo más sencillo posible que muestre el problema. Todos estos detalles contribuyen a aumentar las posibilidades de que su pregunta se responda rápidamente.

## <a name="visual-studio-developer-community"></a>Comunidad de desarrolladores de Visual Studio

A veces los problemas pueden ser difíciles de resolver o irresolubles. Tales situaciones se presentan debido a errores de tecnología, dificultades para aplicar la tecnología a escenarios determinados o a la falta de compatibilidad con escenarios concretos. Esta información es importante para Microsoft y puede proporcionarse a través del sitio de la [comunidad de desarrolladores de Visual Studio](https://developercommunity.visualstudio.com/) .

Los elementos que se publican en el centro de comentarios del producto de WPF se enrutan a la base de datos de errores interna del equipo de WPF. Por lo tanto, es la forma más confiable de obtener sus comentarios sobre el propietario de la característica de WPF. Además, puede validar y realizar un seguimiento de las sugerencias y los errores, así como votar sobre ellos, lo que ayuda al equipo de WPF a priorizar los problemas.

### <a name="developer-community-best-practices"></a>Prácticas recomendadas de la comunidad de desarrolladores

Al publicar en la comunidad de desarrolladores de Visual Studio, la búsqueda de publicaciones existentes, que proporcionan un título significativo y el contenido adecuado, son procedimientos recomendados importantes, al igual que para la publicación en el foro de WPF. A continuación se muestran los procedimientos recomendados adicionales que también debería emplear.

#### <a name="search-existing-posts"></a>Buscar publicaciones existentes

Algunos problemas se producen con tanta frecuencia que otras personas ya se han enfrentado antes a ellos. Por lo tanto, puede resolver el problema rápidamente o puede Agregar la entrada a un problema existente.

#### <a name="use-meaningful-titles"></a>Usar títulos significativos

Los títulos concisos y significativos aumentan la probabilidad de que el problema se dirija al equipo de WPF más adecuado en el menor tiempo posible. Esto es especialmente importante para una tecnología como WPF, que contiene muchas características interrelacionadas.

#### <a name="describe-how-to-reproduce-your-bug"></a>Describir cómo reproducir el error

Al publicar sobre un error, es importante incluir lo siguiente cuando corresponda:

- Proporcione una descripción clara del error.
- Utilice fragmentos de código para respaldar la descripción del error.
- Proporcione una lista de pasos que muestren cómo reproducir el error.
- Incluya el código de ejemplo más pequeño posible que reproduzca el error.
- Mencione si el error se puede reproducir consistentemente o no.
- Incluya la información de excepciones pertinente.

 Si el error está relacionado con la instalación o configuración, adjunte los registros de instalación pertinentes y las instantáneas (archivos prefijados con "dd_" que se encuentran en la carpeta %temp%).

 En el caso de problemas de compilación, adjunte los registros de compilación. El sistema MSBuild puede configurarse para admitir el registro con varios niveles de detalle mediante el uso del modificador/v: desde la línea de comandos o configurando el nivel adecuado desde un entorno de desarrollo integrado (IDE) como Visual Studio.

#### <a name="provide-environment-information"></a>Proporcionar información de entorno

La información general puede resultar útil para agregar contexto a su publicación. En concreto, mencione la plataforma de sistema operativo, la familia de procesadores y la arquitectura, como "Windows 10 versión 1709, Intel (R) Xeon (R), x64".

Si el problema que está publicando está relacionado con la representación, también debe incluir detalles de tarjeta y del controlador de gráficos, si es posible. Esta información es importante porque WPF es un marco de presentación.

#### <a name="provide-solution-or-project-information"></a>Proporcionar información de solución o proyecto

Los errores pueden pertenecer a las herramientas utilizadas para desarrollar y compilar las aplicaciones y los tipos de aplicaciones que se va a compilar. Por lo tanto, puede ser útil especificar:

- El tipo de aplicación que está creando, como:
  - Aplicación ( *. exe*) o biblioteca ( *. dll*)
  - Aplicación de explorador de lenguaje XAML (XAML) (XBAP)
  - Aplicación XAML floja
  - Aplicaciones instaladas de forma independiente
  - Aplicaciones implementadas con ClickOnce independientes
- La herramienta de desarrollo, como:
  - MSBuild
  - Diseñador gráfico de expresiones
  - Diseñador interactivo de expresiones
  - Visual Studio
- La configuración de soluciones, como:
  - Una solución
  - Un solo proyecto
  - Una solución con varios proyectos dependientes
- Si la aplicación tiene recursos neutrales o específicos del idioma. Por ejemplo, ¿especificó la propiedad del proyecto `UICulture` o metadatos localizables para los tipos `Application`, `Page` y `Resource`?
- Si utilizó la configuración neutral de idioma en el archivo AssemblyInfo.cs o AssemblyInfo.vb.

#### <a name="provide-scenario-and-impact-information"></a>Proporcionar información sobre el escenario y el impacto

Proporcione información sobre el escenario que manifiesta el error y su impacto. Esta información es muy importante para el equipo de WPF cuando decide, Cuándo y cómo se debe corregir un problema, o si en su lugar se puede usar una solución alternativa aceptable.

Normalmente, los escenarios de pérdida de datos y bloqueo son de alto impacto y, por lo tanto, los más fáciles para establecer prioridades. Sin embargo, algunos errores solo aparecen en escenarios poco comunes, que también pueden ser los escenarios principales en algunos casos. Proporcionar el contexto alrededor del escenario y el impacto ayuda al equipo de WPF a tomar la decisión adecuada.

## <a name="see-also"></a>Consulte también

- [Cómo notificar un problema con Visual Studio 2017](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)
