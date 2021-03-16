---
title: API no admitidas en .NET Core y .NET 5+
titleSuffix: ''
description: Obtenga información sobre qué API de .NET siempre inician una excepción en .NET Core y .NET 5 y versiones posteriores.
ms.date: 10/13/2020
ms.openlocfilehash: b0dc425bf5f7d8f2a44f51ffe75ffcb0c8a5a7ae
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256262"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="c7372-103">API que siempre inician excepciones en .NET Core y .NET 5+</span><span class="sxs-lookup"><span data-stu-id="c7372-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="c7372-104">Las API siguientes siempre iniciarán una excepción <xref:System.PlatformNotSupportedException> en .NET 5 y versiones posteriores (incluidas todas las versiones de .NET Core) en todas las plataformas, o bien en un subconjunto de estas.</span><span class="sxs-lookup"><span data-stu-id="c7372-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="c7372-105">En este artículo, las API afectadas se organizan por espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c7372-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c7372-106">Este artículo sigue en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="c7372-106">This article is a work-in-progress.</span></span> <span data-ttu-id="c7372-107">No es una lista completa de las API que inician excepciones en .NET 5+.</span><span class="sxs-lookup"><span data-stu-id="c7372-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="c7372-108">En este artículo no se incluyen las implementaciones de interfaz explícitas para la serialización binaria que inician excepciones en .NET 5+.</span><span class="sxs-lookup"><span data-stu-id="c7372-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="c7372-109">Para obtener más información, vea [Serialización binaria en .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="c7372-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="c7372-110">Sistema</span><span class="sxs-lookup"><span data-stu-id="c7372-110">System</span></span>

| <span data-ttu-id="c7372-111">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-111">Member</span></span> | <span data-ttu-id="c7372-112">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-113">All</span><span class="sxs-lookup"><span data-stu-id="c7372-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="c7372-114">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="c7372-115">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="c7372-116">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-117">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="c7372-118">All</span><span class="sxs-lookup"><span data-stu-id="c7372-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="c7372-119">All</span><span class="sxs-lookup"><span data-stu-id="c7372-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="c7372-120">All</span><span class="sxs-lookup"><span data-stu-id="c7372-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-121">All</span><span class="sxs-lookup"><span data-stu-id="c7372-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="c7372-122">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="c7372-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="c7372-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="c7372-124">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-124">Member</span></span> | <span data-ttu-id="c7372-125">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-126">All</span><span class="sxs-lookup"><span data-stu-id="c7372-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-127">All</span><span class="sxs-lookup"><span data-stu-id="c7372-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-128">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="c7372-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="c7372-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="c7372-130">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-130">Member</span></span> | <span data-ttu-id="c7372-131">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-132">All</span><span class="sxs-lookup"><span data-stu-id="c7372-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-133">All</span><span class="sxs-lookup"><span data-stu-id="c7372-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c7372-134">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="c7372-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="c7372-135">System.Configuration</span></span>

| <span data-ttu-id="c7372-136">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-136">Member</span></span> | <span data-ttu-id="c7372-137">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="c7372-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="c7372-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="c7372-139">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="c7372-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="c7372-140">System.Console</span></span>

| <span data-ttu-id="c7372-141">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-141">Member</span></span> | <span data-ttu-id="c7372-142">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="c7372-143">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-143">Linux and macOS</span></span> |
| <span data-ttu-id="c7372-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-145">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-145">Linux and macOS</span></span> |
| <span data-ttu-id="c7372-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-147">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-147">Linux and macOS</span></span> |
| <span data-ttu-id="c7372-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-149">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-149">Linux and macOS</span></span> |
| <span data-ttu-id="c7372-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="c7372-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="c7372-151">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-152">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-153">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-154">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-154">Linux and macOS</span></span> |
| <span data-ttu-id="c7372-155"><xref:System.Console.Title?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="c7372-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="c7372-156">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-156">Linux and macOS</span></span> |
| <span data-ttu-id="c7372-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-158">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-158">Linux and macOS</span></span> |
| <span data-ttu-id="c7372-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-160">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-160">Linux and macOS</span></span> |
| <span data-ttu-id="c7372-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-162">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-162">Linux and macOS</span></span> |
| <span data-ttu-id="c7372-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-164">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="c7372-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="c7372-165">System.Data.Common</span></span>

| <span data-ttu-id="c7372-166">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-166">Member</span></span> | <span data-ttu-id="c7372-167">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="c7372-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (genera <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="c7372-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="c7372-169">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="c7372-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="c7372-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="c7372-171">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-171">Member</span></span> | <span data-ttu-id="c7372-172">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="c7372-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-174">Linux</span><span class="sxs-lookup"><span data-stu-id="c7372-174">Linux</span></span> |
| <span data-ttu-id="c7372-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-176">Linux</span><span class="sxs-lookup"><span data-stu-id="c7372-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="c7372-177">macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="c7372-178">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start(System.String,System.String,System.String,System.Security.SecureString,System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7372-179">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start(System.String,System.String,System.Security.SecureString,System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7372-180">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="c7372-181">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="c7372-182">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="c7372-183">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-183">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="c7372-184">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-184">Linux and macOS</span></span> |
| <span data-ttu-id="c7372-185"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-185"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-186">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-186">Linux and macOS</span></span> |
| <span data-ttu-id="c7372-187"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="c7372-187"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="c7372-188">macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-188">macOS</span></span> |
| <span data-ttu-id="c7372-189"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-189"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-190">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-190">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="c7372-191">System.IO</span><span class="sxs-lookup"><span data-stu-id="c7372-191">System.IO</span></span>

| <span data-ttu-id="c7372-192">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-192">Member</span></span> | <span data-ttu-id="c7372-193">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-193">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-194">All</span><span class="sxs-lookup"><span data-stu-id="c7372-194">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-195">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-195">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="c7372-196">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="c7372-196">System.IO.Pipes</span></span>

| <span data-ttu-id="c7372-197">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-197">Member</span></span> | <span data-ttu-id="c7372-198">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-198">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="c7372-199">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="c7372-200">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="c7372-201">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-201">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="c7372-202">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-202">Linux and macOS</span></span> |
| <span data-ttu-id="c7372-203"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-203"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-204">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-204">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="c7372-205">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-205">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="c7372-206">System.Media</span><span class="sxs-lookup"><span data-stu-id="c7372-206">System.Media</span></span>

| <span data-ttu-id="c7372-207">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-207">Member</span></span> | <span data-ttu-id="c7372-208">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-208">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-209">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-209">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="c7372-210">System.Net</span><span class="sxs-lookup"><span data-stu-id="c7372-210">System.Net</span></span>

| <span data-ttu-id="c7372-211">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-211">Member</span></span> | <span data-ttu-id="c7372-212">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-212">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="c7372-213">All</span><span class="sxs-lookup"><span data-stu-id="c7372-213">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="c7372-214">All</span><span class="sxs-lookup"><span data-stu-id="c7372-214">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-215">All</span><span class="sxs-lookup"><span data-stu-id="c7372-215">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-216">All</span><span class="sxs-lookup"><span data-stu-id="c7372-216">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-217">All</span><span class="sxs-lookup"><span data-stu-id="c7372-217">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-218">All</span><span class="sxs-lookup"><span data-stu-id="c7372-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-219">All</span><span class="sxs-lookup"><span data-stu-id="c7372-219">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-220">All</span><span class="sxs-lookup"><span data-stu-id="c7372-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-221">All</span><span class="sxs-lookup"><span data-stu-id="c7372-221">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-222">All</span><span class="sxs-lookup"><span data-stu-id="c7372-222">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-223">All</span><span class="sxs-lookup"><span data-stu-id="c7372-223">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="c7372-224">All</span><span class="sxs-lookup"><span data-stu-id="c7372-224">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-225">All</span><span class="sxs-lookup"><span data-stu-id="c7372-225">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-226">All</span><span class="sxs-lookup"><span data-stu-id="c7372-226">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-227">All</span><span class="sxs-lookup"><span data-stu-id="c7372-227">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-228">All</span><span class="sxs-lookup"><span data-stu-id="c7372-228">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-229">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-229">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="c7372-230">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="c7372-230">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="c7372-231">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-231">Member</span></span> | <span data-ttu-id="c7372-232">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-232">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-233">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="c7372-233">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="c7372-234">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="c7372-234">System.Net.Sockets</span></span>

| <span data-ttu-id="c7372-235">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-235">Member</span></span> | <span data-ttu-id="c7372-236">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-236">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="c7372-237">All</span><span class="sxs-lookup"><span data-stu-id="c7372-237">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="c7372-238">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-238">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="c7372-239">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="c7372-239">System.Net.WebSockets</span></span>

| <span data-ttu-id="c7372-240">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-240">Member</span></span> | <span data-ttu-id="c7372-241">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-241">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="c7372-242">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-242">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="c7372-243">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="c7372-243">System.Reflection</span></span>

| <span data-ttu-id="c7372-244">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-244">Member</span></span> | <span data-ttu-id="c7372-245">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-245">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-246">All</span><span class="sxs-lookup"><span data-stu-id="c7372-246">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7372-247">All</span><span class="sxs-lookup"><span data-stu-id="c7372-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-248">All</span><span class="sxs-lookup"><span data-stu-id="c7372-248">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c7372-249">All</span><span class="sxs-lookup"><span data-stu-id="c7372-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="c7372-250">All</span><span class="sxs-lookup"><span data-stu-id="c7372-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-251">All</span><span class="sxs-lookup"><span data-stu-id="c7372-251">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="c7372-252">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-252">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="c7372-253">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="c7372-253">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="c7372-254">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-254">Member</span></span> | <span data-ttu-id="c7372-255">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-255">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="c7372-256">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-256">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="c7372-257">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="c7372-257">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="c7372-258">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-258">Member</span></span> | <span data-ttu-id="c7372-259">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-259">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c7372-260">All</span><span class="sxs-lookup"><span data-stu-id="c7372-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="c7372-261">All</span><span class="sxs-lookup"><span data-stu-id="c7372-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="c7372-262">All</span><span class="sxs-lookup"><span data-stu-id="c7372-262">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="c7372-263">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-263">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7372-264">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="c7372-265">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-265">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="c7372-266">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-266">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="c7372-267">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="c7372-267">System.Runtime.Serialization</span></span>

| <span data-ttu-id="c7372-268">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-268">Member</span></span> | <span data-ttu-id="c7372-269">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-269">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="c7372-270">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-270">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="c7372-271">System.Security</span><span class="sxs-lookup"><span data-stu-id="c7372-271">System.Security</span></span>

| <span data-ttu-id="c7372-272">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-272">Member</span></span> | <span data-ttu-id="c7372-273">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-273">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="c7372-274">All</span><span class="sxs-lookup"><span data-stu-id="c7372-274">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="c7372-275">All</span><span class="sxs-lookup"><span data-stu-id="c7372-275">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7372-276">All</span><span class="sxs-lookup"><span data-stu-id="c7372-276">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="c7372-277">All</span><span class="sxs-lookup"><span data-stu-id="c7372-277">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="c7372-278">All</span><span class="sxs-lookup"><span data-stu-id="c7372-278">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="c7372-279">All</span><span class="sxs-lookup"><span data-stu-id="c7372-279">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="c7372-280">All</span><span class="sxs-lookup"><span data-stu-id="c7372-280">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="c7372-281">All</span><span class="sxs-lookup"><span data-stu-id="c7372-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="c7372-282">All</span><span class="sxs-lookup"><span data-stu-id="c7372-282">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="c7372-283">All</span><span class="sxs-lookup"><span data-stu-id="c7372-283">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="c7372-284">All</span><span class="sxs-lookup"><span data-stu-id="c7372-284">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c7372-285">All</span><span class="sxs-lookup"><span data-stu-id="c7372-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="c7372-286">All</span><span class="sxs-lookup"><span data-stu-id="c7372-286">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="c7372-287">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-287">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="c7372-288">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="c7372-288">System.Security.Claims</span></span>

| <span data-ttu-id="c7372-289">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-289">Member</span></span> | <span data-ttu-id="c7372-290">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-290">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-291">All</span><span class="sxs-lookup"><span data-stu-id="c7372-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-292">All</span><span class="sxs-lookup"><span data-stu-id="c7372-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="c7372-293">All</span><span class="sxs-lookup"><span data-stu-id="c7372-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-294">All</span><span class="sxs-lookup"><span data-stu-id="c7372-294">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-295">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-295">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="c7372-296">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="c7372-296">System.Security.Cryptography</span></span>

| <span data-ttu-id="c7372-297">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-297">Member</span></span> | <span data-ttu-id="c7372-298">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-298">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7372-299">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-299">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="c7372-300">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="c7372-301">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="c7372-302">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="c7372-303">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="c7372-304">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="c7372-305">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="c7372-306">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="c7372-307">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="c7372-308">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="c7372-309">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="c7372-310">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="c7372-311">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="c7372-312">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-312">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="c7372-313">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="c7372-314">All</span><span class="sxs-lookup"><span data-stu-id="c7372-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7372-315">All</span><span class="sxs-lookup"><span data-stu-id="c7372-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-316">All</span><span class="sxs-lookup"><span data-stu-id="c7372-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-317">All</span><span class="sxs-lookup"><span data-stu-id="c7372-317">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-318">All</span><span class="sxs-lookup"><span data-stu-id="c7372-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="c7372-319">All</span><span class="sxs-lookup"><span data-stu-id="c7372-319">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7372-320">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-320">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-321">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-322">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="c7372-322">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-323">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-323">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-324">All</span><span class="sxs-lookup"><span data-stu-id="c7372-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="c7372-325">All</span><span class="sxs-lookup"><span data-stu-id="c7372-325">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c7372-326">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-326">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="c7372-327">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="c7372-327">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="c7372-328">Member</span><span class="sxs-lookup"><span data-stu-id="c7372-328">Member</span></span> | <span data-ttu-id="c7372-329">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-329">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="c7372-330">All</span><span class="sxs-lookup"><span data-stu-id="c7372-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="c7372-331">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="c7372-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="c7372-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="c7372-333">Miembro</span><span class="sxs-lookup"><span data-stu-id="c7372-333">Member</span></span> | <span data-ttu-id="c7372-334">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-335">All</span><span class="sxs-lookup"><span data-stu-id="c7372-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-336">All</span><span class="sxs-lookup"><span data-stu-id="c7372-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-337">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-337">All</span></span> |
| <span data-ttu-id="c7372-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="c7372-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c7372-339">Todos</span><span class="sxs-lookup"><span data-stu-id="c7372-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="c7372-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="c7372-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="c7372-341">Miembro</span><span class="sxs-lookup"><span data-stu-id="c7372-341">Member</span></span> | <span data-ttu-id="c7372-342">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-343">Todos</span><span class="sxs-lookup"><span data-stu-id="c7372-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="c7372-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="c7372-344">System.Security.Policy</span></span>

| <span data-ttu-id="c7372-345">Miembro</span><span class="sxs-lookup"><span data-stu-id="c7372-345">Member</span></span> | <span data-ttu-id="c7372-346">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-347">Todos</span><span class="sxs-lookup"><span data-stu-id="c7372-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="c7372-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="c7372-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="c7372-349">Miembro</span><span class="sxs-lookup"><span data-stu-id="c7372-349">Member</span></span> | <span data-ttu-id="c7372-350">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c7372-351">Todos</span><span class="sxs-lookup"><span data-stu-id="c7372-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="c7372-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="c7372-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="c7372-353">Miembro</span><span class="sxs-lookup"><span data-stu-id="c7372-353">Member</span></span> | <span data-ttu-id="c7372-354">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-355">Todos</span><span class="sxs-lookup"><span data-stu-id="c7372-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="c7372-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="c7372-356">System.Threading</span></span>

| <span data-ttu-id="c7372-357">Miembro</span><span class="sxs-lookup"><span data-stu-id="c7372-357">Member</span></span> | <span data-ttu-id="c7372-358">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-359">All</span><span class="sxs-lookup"><span data-stu-id="c7372-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c7372-360">All</span><span class="sxs-lookup"><span data-stu-id="c7372-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="c7372-361">All</span><span class="sxs-lookup"><span data-stu-id="c7372-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="c7372-362">All</span><span class="sxs-lookup"><span data-stu-id="c7372-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="c7372-363">All</span><span class="sxs-lookup"><span data-stu-id="c7372-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="c7372-364">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="c7372-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="c7372-365">System.Xml</span></span>

| <span data-ttu-id="c7372-366">Miembro</span><span class="sxs-lookup"><span data-stu-id="c7372-366">Member</span></span> | <span data-ttu-id="c7372-367">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="c7372-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="c7372-368">All</span><span class="sxs-lookup"><span data-stu-id="c7372-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="c7372-369">All</span><span class="sxs-lookup"><span data-stu-id="c7372-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="c7372-370">Todas</span><span class="sxs-lookup"><span data-stu-id="c7372-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="c7372-371">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7372-371">See also</span></span>

- [<span data-ttu-id="c7372-372">Cambios importantes para la migración desde .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="c7372-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="c7372-373">Serialización binaria en .NET Core</span><span class="sxs-lookup"><span data-stu-id="c7372-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="c7372-374">Analizador de portabilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="c7372-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
