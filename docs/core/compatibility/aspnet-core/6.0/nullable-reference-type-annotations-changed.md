---
title: 'Cambio importante: las anotaciones en los tipos de referencia que aceptan valores NULL han cambiado'
description: Obtenga información sobre el cambio importante en ASP.NET Core 6.0 que lleva por título "Las anotaciones en los tipos de referencia que aceptan valores NULL han cambiado".
author: scottaddie
ms.author: scaddie
ms.date: 02/24/2021
ms.openlocfilehash: d289ee68a10ee6a237e553a9e0ade153add8f608
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257894"
---
# <a name="nullable-reference-type-annotations-changed"></a><span data-ttu-id="d1b92-103">Las anotaciones en los tipos de referencia que aceptan valores NULL han cambiado.</span><span class="sxs-lookup"><span data-stu-id="d1b92-103">Nullable reference type annotations changed</span></span>

<span data-ttu-id="d1b92-104">_**Esta incidencia representa un trabajo en curso. Todos los cambios importantes en las anotaciones de nulabilidad se agregarán a esta incidencia a lo largo de ASP.NET Core 6.0.**_</span><span class="sxs-lookup"><span data-stu-id="d1b92-104">_**This issue represents a work-in-progress. All breaking changes to nullability annotations will be aggregated into this issue throughout the course of ASP.NET Core 6.0.**_</span></span>

<span data-ttu-id="d1b92-105">A partir de ASP.NET Core 5.0, las anotaciones de nulabilidad se han aplicado a partes del código.</span><span class="sxs-lookup"><span data-stu-id="d1b92-105">Starting in ASP.NET Core 5.0, nullability annotations have been applied to parts of the code.</span></span> <span data-ttu-id="d1b92-106">Desde el principio de este esfuerzo, [se esperaban errores](https://github.com/dotnet/runtime/blob/master/docs/coding-guidelines/api-guidelines/nullability.md#breaking-change-guidance) en estas anotaciones y es necesario realizar correcciones.</span><span class="sxs-lookup"><span data-stu-id="d1b92-106">From the outset of this effort, [mistakes were expected](https://github.com/dotnet/runtime/blob/master/docs/coding-guidelines/api-guidelines/nullability.md#breaking-change-guidance) in these annotations and fixes would need to be made.</span></span> <span data-ttu-id="d1b92-107">En ASP.NET Core 6.0, se están actualizando algunas anotaciones aplicadas previamente.</span><span class="sxs-lookup"><span data-stu-id="d1b92-107">In ASP.NET Core 6.0, some previously applied annotations are being updated.</span></span> <span data-ttu-id="d1b92-108">Algunos de estos cambios se consideran cambios importantes en el origen.</span><span class="sxs-lookup"><span data-stu-id="d1b92-108">Some of these changes are considered source breaking changes.</span></span> <span data-ttu-id="d1b92-109">Los cambios conducen a que las API sean incompatibles o más restrictivas.</span><span class="sxs-lookup"><span data-stu-id="d1b92-109">The changes lead to the APIs being incompatible or more restrictive.</span></span> <span data-ttu-id="d1b92-110">Las API actualizadas pueden producir advertencias en tiempo de compilación cuando se usan en proyectos que tienen habilitados los tipos de referencia que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="d1b92-110">The updated APIs may result in build-time warnings when used in projects that have nullable reference types enabled.</span></span>

<span data-ttu-id="d1b92-111">Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#27564](https://github.com/dotnet/aspnetcore/issues/27564).</span><span class="sxs-lookup"><span data-stu-id="d1b92-111">For discussion, see GitHub issue [dotnet/aspnetcore#27564](https://github.com/dotnet/aspnetcore/issues/27564).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d1b92-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d1b92-112">Version introduced</span></span>

<span data-ttu-id="d1b92-113">6.0</span><span class="sxs-lookup"><span data-stu-id="d1b92-113">6.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="d1b92-114">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="d1b92-114">Old behavior</span></span>

<span data-ttu-id="d1b92-115">Las API afectadas tienen anotaciones de tipo de referencia que aceptan valores NULL incorrectas.</span><span class="sxs-lookup"><span data-stu-id="d1b92-115">The affected APIs have incorrect nullable reference type annotations.</span></span> <span data-ttu-id="d1b92-116">Las advertencias de compilación faltan o son incorrectas.</span><span class="sxs-lookup"><span data-stu-id="d1b92-116">Build warnings are either absent or incorrect.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="d1b92-117">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="d1b92-117">New behavior</span></span>

<span data-ttu-id="d1b92-118">Se generan nuevas advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="d1b92-118">New build warnings are produced.</span></span> <span data-ttu-id="d1b92-119">Ya no se generan advertencias de compilación incorrectas para las API afectadas.</span><span class="sxs-lookup"><span data-stu-id="d1b92-119">Incorrect build warnings are no longer produced for the affected APIs.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d1b92-120">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="d1b92-120">Reason for change</span></span>

<span data-ttu-id="d1b92-121">Gracias a comentarios y pruebas adicionales, se ha determinado que las anotaciones que aceptan valores NULL de las API afectadas eran inexactas.</span><span class="sxs-lookup"><span data-stu-id="d1b92-121">Through feedback and further testing, the nullable annotations for the affected APIs were determined to be inaccurate.</span></span> <span data-ttu-id="d1b92-122">Las anotaciones actualizadas representan ahora correctamente los contratos de nulabilidad de las API.</span><span class="sxs-lookup"><span data-stu-id="d1b92-122">The updated annotations now correctly represent the nullability contracts for the APIs.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d1b92-123">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d1b92-123">Recommended action</span></span>

<span data-ttu-id="d1b92-124">Actualice el código que llama a estas API para reflejar los contratos de nulabilidad revisados.</span><span class="sxs-lookup"><span data-stu-id="d1b92-124">Update code calling these APIs to reflect the revised nullability contracts.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d1b92-125">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d1b92-125">Affected APIs</span></span>

* <xref:Microsoft.AspNetCore.Components.ParameterView.FromDictionary%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Components.RenderTree.Renderer.DispatchEventAsync%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeEdit.RemovedAttributeName?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Authentication.AuthenticationSchemeOptions.ForwardDefaultSelector%2A?displayProperty=nameWithType>
* <xref:Microsoft.Net.Http.Headers.RangeConditionHeaderValue.%23ctor%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Connections.IConnectionListener.AcceptAsync%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.Infrastructure.IApplicationDiscriminator.Discriminator%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.DataProtectionOptions.ApplicationDiscriminator%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.AuthenticatedEncryptorFactory.CreateEncryptorInstance%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.CngCbcAuthenticatedEncryptorFactory.CreateEncryptorInstance%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.CngGcmAuthenticatedEncryptorFactory.CreateEncryptorInstance%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.IAuthenticatedEncryptorFactory.CreateEncryptorInstance%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.ManagedAuthenticatedEncryptorFactory.CreateEncryptorInstance%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.KeyManagement.IKey.CreateEncryptor%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.KeyManagement.KeyManagementOptions.AuthenticatedEncryptorConfiguration%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.KeyManagement.KeyManagementOptions.XmlEncryptor%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.KeyManagement.KeyManagementOptions.XmlRepository%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.XmlEncryption.ICertificateResolver.ResolveCertificate%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.DataProtectionUtilityExtensions.GetApplicationUniqueIdentifier%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.Repositories.FileSystemXmlRepository.DefaultKeyStorageDirectory%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.Repositories.RegistryXmlRepository.DefaultRegistryKey%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.XmlEncryption.CertificateResolver.ResolveCertificate%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Http.Endpoint.%23ctor%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Http.Endpoint.RequestDelegate%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Routing.RouteValueDictionary.TryAdd%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Routing.LinkGenerator.GetUriByAddress%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Http.Features.IFeatureCollection.Set%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Http.Features.FeatureCollection.Set%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Http.Features.IFeatureCollection.Get%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Authentication.Cookies.ITicketStore.RetrieveAsync%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Http.Features.IFeatureCollection.Get%60%601?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Http.Features.IFeatureCollection.Set%60%601(%60%600)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Http.Features.FeatureCollection.Set%60%601(%60%600)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Mvc.ModelBinding.ModelStateDictionary.SetModelValue(System.String,System.Object,System.String)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Mvc.ModelBinding.ModelStateDictionary.Item(System.String)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ClientValidatorItem.%23ctor%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ClientValidatorItem.Validator%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Http.Endpoint.%23ctor%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Routing.RouteValueDictionary.TryAdd(System.String,System.Object)?displayProperty=nameWithType>>
* <xref:Microsoft.AspNetCore.Routing.LinkGenerator.GetUriByAddress%60%601(%60%600,Microsoft.AspNetCore.Routing.RouteValueDictionary,System.String,Microsoft.AspNetCore.Http.HostString,Microsoft.AspNetCore.Http.PathString,Microsoft.AspNetCore.Http.FragmentString,Microsoft.AspNetCore.Routing.LinkOptions)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.Infrastructure.IApplicationDiscriminator.Discriminator?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.DataProtectionOptions.ApplicationDiscriminator?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.AuthenticatedEncryptorFactory.CreateEncryptorInstance(Microsoft.AspNetCore.DataProtection.KeyManagement.IKey)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.CngCbcAuthenticatedEncryptorFactory.CreateEncryptorInstance(Microsoft.AspNetCore.DataProtection.KeyManagement.IKey)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.CngGcmAuthenticatedEncryptorFactory.CreateEncryptorInstance(Microsoft.AspNetCore.DataProtection.KeyManagement.IKey)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.IAuthenticatedEncryptorFactory.CreateEncryptorInstance(Microsoft.AspNetCore.DataProtection.KeyManagement.IKey)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.ManagedAuthenticatedEncryptorFactory.CreateEncryptorInstance(Microsoft.AspNetCore.DataProtection.KeyManagement.IKey)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.KeyManagement.IKey.CreateEncryptor?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.KeyManagement.KeyManagementOptions.AuthenticatedEncryptorConfiguration?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.KeyManagement.KeyManagementOptions.XmlEncryptor?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.KeyManagement.KeyManagementOptions.XmlRepository?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.XmlEncryption.ICertificateResolver.ResolveCertificate(System.String)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.DataProtectionUtilityExtensions.GetApplicationUniqueIdentifier(System.IServiceProvider)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.Repositories.FileSystemXmlRepository.DefaultKeyStorageDirectory?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.Repositories.RegistryXmlRepository.DefaultRegistryKey?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.DataProtection.XmlEncryption.CertificateResolver.ResolveCertificate(System.String)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Connections.IConnectionListener.AcceptAsync(System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Authentication.AuthenticationSchemeOptions.ForwardDefaultSelector?displayProperty=nameWithType>
* <xref:Microsoft.Net.Http.Headers.RangeConditionHeaderValue.%23ctor(Microsoft.Net.Http.Headers.EntityTagHeaderValue)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.Http.Connections.Features.IHttpContextFeature.HttpContext%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.Protocol.CompletionMessage.WithError%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.Protocol.CompletionMessage.WithResult%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.Protocol.HubMethodInvocationMessage.Arguments%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.Protocol.HubMethodInvocationMessage.%23ctor(System.String,System.String,System.Object[])?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.Protocol.HubMethodInvocationMessage.%23ctor(System.String,System.String,System.Object[],System.String[])?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.Protocol.InvocationMessage.%23ctor(System.String,System.Object[])?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.Protocol.InvocationMessage.%23ctor(System.String,System.String,System.Object[])?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.Protocol.InvocationMessage.%23ctor(System.String,System.String,System.Object[],System.String[])?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.Protocol.StreamInvocationMessage.%23ctor(System.String,System.String,System.Object[])?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.Protocol.StreamInvocationMessage.%23ctor(System.String,System.String,System.Object[],System.String[])?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.Protocol.IHubProtocol.TryParseMessage(System.Buffers.ReadOnlySequence{System.Byte}@,Microsoft.AspNetCore.SignalR.IInvocationBinder,Microsoft.AspNetCore.SignalR.Protocol.HubMessage@)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendAllAsync(System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendAllExceptAsync(System.String,System.Object[],System.Collections.Generic.IReadOnlyList{System.String},System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendConnectionAsync(System.String,System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendConnectionsAsync(System.Collections.Generic.IReadOnlyList{System.String},System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendGroupAsync(System.String,System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendGroupExceptAsync(System.String,System.String,System.Object[],System.Collections.Generic.IReadOnlyList{System.String},System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendGroupsAsync(System.Collections.Generic.IReadOnlyList{System.String},System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendUserAsync(System.String,System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendUsersAsync(System.Collections.Generic.IReadOnlyList{System.String},System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendAllAsync(System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendAllExceptAsync(System.String,System.Object[],System.Collections.Generic.IReadOnlyList{System.String},System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendConnectionAsync(System.String,System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendConnectionsAsync(System.Collections.Generic.IReadOnlyList{System.String},System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendGroupAsync(System.String,System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendGroupExceptAsync(System.String,System.String,System.Object[],System.Collections.Generic.IReadOnlyList{System.String},System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendGroupsAsync(System.Collections.Generic.IReadOnlyList{System.String},System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendUserAsync(System.String,System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendUsersAsync(System.Collections.Generic.IReadOnlyList{System.String},System.String,System.Object[],System.Threading.CancellationToken)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.IClientProxy.SendCoreAsync%2A?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.User?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.WebUtilities.QueryHelpers.ParseNullableQuery(System.String)?displayProperty=nameWithType>
* <xref:Microsoft.AspNetCore.WebUtilities.QueryHelpers.ParseQuery(System.String)?displayProperty=nameWithType>

## <a name="see-also"></a><span data-ttu-id="d1b92-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1b92-126">See also</span></span>

- [<span data-ttu-id="d1b92-127">Cambios en las anotaciones de tipos de referencia que aceptan valores NULL en las bibliotecas .NET básicas</span><span class="sxs-lookup"><span data-stu-id="d1b92-127">Nullable reference type annotation changes in core .NET libraries</span></span>](../../core-libraries/6.0/nullable-ref-type-annotation-changes.md)

<!--

## Category

ASP.NET Core

## Affected APIs

- `Overload:Microsoft.AspNetCore.Components.ParameterView.FromDictionary`
- `Overload:Microsoft.AspNetCore.Components.RenderTree.Renderer.DispatchEventAsync`
- `F:Microsoft.AspNetCore.Components.RenderTree.RenderTreeEdit.RemovedAttributeName`
- `Overload:Microsoft.AspNetCore.Authentication.AuthenticationSchemeOptions.ForwardDefaultSelector`
- `Overload:Microsoft.Net.Http.Headers.RangeConditionHeaderValue.#ctor`
- `Overload:Microsoft.AspNetCore.Connections.IConnectionListener.AcceptAsync`
- `Overload:Microsoft.AspNetCore.DataProtection.Infrastructure.IApplicationDiscriminator.Discriminator`
- `Overload:Microsoft.AspNetCore.DataProtection.DataProtectionOptions.ApplicationDiscriminator`
- `Overload:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.AuthenticatedEncryptorFactory.CreateEncryptorInstance`
- `Overload:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.CngCbcAuthenticatedEncryptorFactory.CreateEncryptorInstance`
- `Overload:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.CngGcmAuthenticatedEncryptorFactory.CreateEncryptorInstance`
- `Overload:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.IAuthenticatedEncryptorFactory.CreateEncryptorInstance`
- `Overload:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.ManagedAuthenticatedEncryptorFactory.CreateEncryptorInstance`
- `Overload:Microsoft.AspNetCore.DataProtection.KeyManagement.IKey.CreateEncryptor`
- `Overload:Microsoft.AspNetCore.DataProtection.KeyManagement.KeyManagementOptions.AuthenticatedEncryptorConfiguration`
- `Overload:Microsoft.AspNetCore.DataProtection.KeyManagement.KeyManagementOptions.XmlEncryptor`
- `Overload:Microsoft.AspNetCore.DataProtection.KeyManagement.KeyManagementOptions.XmlRepository`
- `Overload:Microsoft.AspNetCore.DataProtection.XmlEncryption.ICertificateResolver.ResolveCertificate`
- `Overload:Microsoft.AspNetCore.DataProtection.DataProtectionUtilityExtensions.GetApplicationUniqueIdentifier`
- `Overload:Microsoft.AspNetCore.DataProtection.Repositories.FileSystemXmlRepository.DefaultKeyStorageDirectory`
- `Overload:Microsoft.AspNetCore.DataProtection.Repositories.RegistryXmlRepository.DefaultRegistryKey`
- `Overload:Microsoft.AspNetCore.DataProtection.XmlEncryption.CertificateResolver.ResolveCertificate`
- `Overload:Microsoft.AspNetCore.Http.Endpoint.#ctor`
- `Overload:Microsoft.AspNetCore.Http.Endpoint.RequestDelegate`
- `Overload:Microsoft.AspNetCore.Routing.RouteValueDictionary.TryAdd`
- `Overload:Microsoft.AspNetCore.Routing.LinkGenerator.GetUriByAddress`
- `Overload:Microsoft.AspNetCore.Http.Features.IFeatureCollection.Set`
- `Overload:Microsoft.AspNetCore.Http.Features.FeatureCollection.Set`
- `Overload:Microsoft.AspNetCore.Http.Features.IFeatureCollection.Get`
- `Overload:Microsoft.AspNetCore.Authentication.Cookies.ITicketStore.RetrieveAsync`
- `M:Microsoft.AspNetCore.Http.Features.IFeatureCollection.Get%60%601`
- `M:Microsoft.AspNetCore.Http.Features.IFeatureCollection.Set%60%601(%60%600)`
- `M:Microsoft.AspNetCore.Http.Features.FeatureCollection.Set%60%601(%60%600)`
- `M:Microsoft.AspNetCore.Mvc.ModelBinding.ModelStateDictionary.SetModelValue(System.String,System.Object,System.String)`
- `P:Microsoft.AspNetCore.Mvc.ModelBinding.ModelStateDictionary.Item(System.String)`
- `Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ClientValidatorItem.#ctor`
- `Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ClientValidatorItem.Validator`
- `Overload:Microsoft.AspNetCore.Http.Endpoint.#ctor`
- `M:Microsoft.AspNetCore.Routing.RouteValueDictionary.TryAdd(System.String,System.Object)`
- `M:Microsoft.AspNetCore.Routing.LinkGenerator.GetUriByAddress%60%601(%60%600,Microsoft.AspNetCore.Routing.RouteValueDictionary,System.String,Microsoft.AspNetCore.Http.HostString,Microsoft.AspNetCore.Http.PathString,Microsoft.AspNetCore.Http.FragmentString,Microsoft.AspNetCore.Routing.LinkOptions)`
- `P:Microsoft.AspNetCore.DataProtection.Infrastructure.IApplicationDiscriminator.Discriminator`
- `P:Microsoft.AspNetCore.DataProtection.DataProtectionOptions.ApplicationDiscriminator`
- `M:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.AuthenticatedEncryptorFactory.CreateEncryptorInstance(Microsoft.AspNetCore.DataProtection.KeyManagement.IKey)`
- `M:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.CngCbcAuthenticatedEncryptorFactory.CreateEncryptorInstance(Microsoft.AspNetCore.DataProtection.KeyManagement.IKey)`
- `M:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.CngGcmAuthenticatedEncryptorFactory.CreateEncryptorInstance(Microsoft.AspNetCore.DataProtection.KeyManagement.IKey)`
- `M:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.IAuthenticatedEncryptorFactory.CreateEncryptorInstance(Microsoft.AspNetCore.DataProtection.KeyManagement.IKey)`
- `M:Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.ManagedAuthenticatedEncryptorFactory.CreateEncryptorInstance(Microsoft.AspNetCore.DataProtection.KeyManagement.IKey)`
- `M:Microsoft.AspNetCore.DataProtection.KeyManagement.IKey.CreateEncryptor`
- `P:Microsoft.AspNetCore.DataProtection.KeyManagement.KeyManagementOptions.AuthenticatedEncryptorConfiguration`
- `P:Microsoft.AspNetCore.DataProtection.KeyManagement.KeyManagementOptions.XmlEncryptor`
- `P:Microsoft.AspNetCore.DataProtection.KeyManagement.KeyManagementOptions.XmlRepository`
- `M:Microsoft.AspNetCore.DataProtection.XmlEncryption.ICertificateResolver.ResolveCertificate(System.String)`
- `M:Microsoft.AspNetCore.DataProtection.DataProtectionUtilityExtensions.GetApplicationUniqueIdentifier(System.IServiceProvider)`
- `P:Microsoft.AspNetCore.DataProtection.Repositories.FileSystemXmlRepository.DefaultKeyStorageDirectory`
- `P:Microsoft.AspNetCore.DataProtection.Repositories.RegistryXmlRepository.DefaultRegistryKey`
- `M:Microsoft.AspNetCore.DataProtection.XmlEncryption.CertificateResolver.ResolveCertificate(System.String)`
- `M:Microsoft.AspNetCore.Connections.IConnectionListener.AcceptAsync(System.Threading.CancellationToken)`
- `P:Microsoft.AspNetCore.Authentication.AuthenticationSchemeOptions.ForwardDefaultSelector`
- `M:Microsoft.Net.Http.Headers.RangeConditionHeaderValue.#ctor(Microsoft.Net.Http.Headers.EntityTagHeaderValue)`
- `Overload:Microsoft.AspNetCore.Http.Connections.Features.IHttpContextFeature.HttpContext`
- `Overload:Microsoft.AspNetCore.SignalR.Protocol.CompletionMessage.WithError`
- `Overload:Microsoft.AspNetCore.SignalR.Protocol.CompletionMessage.WithResult`
- `Overload:Microsoft.AspNetCore.SignalR.Protocol.HubMethodInvocationMessage.Arguments`
- `M:Microsoft.AspNetCore.SignalR.Protocol.HubMethodInvocationMessage.#ctor(System.String,System.String,System.Object[])`
- `M:Microsoft.AspNetCore.SignalR.Protocol.HubMethodInvocationMessage.#ctor(System.String,System.String,System.Object[],System.String[])`
- `M:Microsoft.AspNetCore.SignalR.Protocol.InvocationMessage.#ctor(System.String,System.Object[])`
- `M:Microsoft.AspNetCore.SignalR.Protocol.InvocationMessage.#ctor(System.String,System.String,System.Object[])`
- `M:Microsoft.AspNetCore.SignalR.Protocol.InvocationMessage.#ctor(System.String,System.String,System.Object[],System.String[])`
- `M:Microsoft.AspNetCore.SignalR.Protocol.StreamInvocationMessage.#ctor(System.String,System.String,System.Object[])`
- `M:Microsoft.AspNetCore.SignalR.Protocol.StreamInvocationMessage.#ctor(System.String,System.String,System.Object[],System.String[])`
- `M:Microsoft.AspNetCore.SignalR.Protocol.IHubProtocol.TryParseMessage(System.Buffers.ReadOnlySequence{System.Byte}@,Microsoft.AspNetCore.SignalR.IInvocationBinder,Microsoft.AspNetCore.SignalR.Protocol.HubMessage@)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendAllAsync(System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendAllExceptAsync(System.String,System.Object[],System.Collections.Generic.IReadOnlyList{System.String},System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendConnectionAsync(System.String,System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendConnectionsAsync(System.Collections.Generic.IReadOnlyList{System.String},System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendGroupAsync(System.String,System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendGroupExceptAsync(System.String,System.String,System.Object[],System.Collections.Generic.IReadOnlyList{System.String},System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendGroupsAsync(System.Collections.Generic.IReadOnlyList{System.String},System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendUserAsync(System.String,System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendUsersAsync(System.Collections.Generic.IReadOnlyList{System.String},System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendAllAsync(System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendAllExceptAsync(System.String,System.Object[],System.Collections.Generic.IReadOnlyList{System.String},System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendConnectionAsync(System.String,System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendConnectionsAsync(System.Collections.Generic.IReadOnlyList{System.String},System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendGroupAsync(System.String,System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendGroupExceptAsync(System.String,System.String,System.Object[],System.Collections.Generic.IReadOnlyList{System.String},System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendGroupsAsync(System.Collections.Generic.IReadOnlyList{System.String},System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendUserAsync(System.String,System.String,System.Object[],System.Threading.CancellationToken)`
- `M:Microsoft.AspNetCore.SignalR.DefaultHubLifetimeManager%601.SendUsersAsync(System.Collections.Generic.IReadOnlyList{System.String},System.String,System.Object[],System.Threading.CancellationToken)`
- `Overload:Microsoft.AspNetCore.SignalR.IClientProxy.SendCoreAsync`
- `P:Microsoft.AspNetCore.SignalR.HubConnectionContext.User`
- `M:Microsoft.AspNetCore.WebUtilities.QueryHelpers.ParseNullableQuery(System.String)`
- `M:Microsoft.AspNetCore.WebUtilities.QueryHelpers.ParseQuery(System.String)`

-->
