--[[
    PHZZX7 HUB - STEAL AN EGG (VERSÃO COMPACTA + POSIÇÃO AJUSTADA)
    Tecla para abrir/fechar: RightControl
    Painel 460x300, aparece mais pra baixo
]]

-- ============ CONFIGURAÇÃO ============
local TOGGLE_KEY = Enum.KeyCode.RightControl

local SCRIPTS = {
    { Nome = "Chilli Hub",   Loader = function() return loadstring(game:HttpGet("https://raw.githubusercontent.com/tienkhanh1/spicy/main/Chilli.lua"))() end },
    { Nome = "Serve PV",     Loader = function() return loadstring(game:HttpGet("https://pastefy.app/YoZocJ8O/raw"))() end },
    { Nome = "Sena Hub",     Loader = function() return loadstring(game:HttpGet("https://senahub.xyz/raw/loader"))() end },
    { Nome = "Pulse Hub",    Loader = function() return loadstring(game:HttpGet("https://raw.githubusercontent.com/PulseZax/Loader/refs/heads/main/.lua"))() end },
    { Nome = "Sources Hub",  Loader = function() return loadstring(game:HttpGet("https://gist.githubusercontent.com/sourceshubs/1737c14cdba5c6fb472a995d555a50f1/raw/SourcesHubInstantStealNew"))() end },
    { Nome = "LKS Hub",      Loader = function() return loadstring(game:HttpGet("https://raw.githubusercontent.com/LucasggkX/LKZ-Hub/refs/heads/main/Loader.lua"))() end },
    { Nome = "Bks Hub",      Loader = function() return loadstring(game:HttpGet("https://api.luarmor.net/files/v4/loaders/307981fffc5ae30456faa083d134af70.lua"))() end },
    { Nome = "Clover Hub",   Loader = function() return loadstring(game:HttpGet("https://cloverhub.app/clover.lua"))() end },
    { Nome = "Fyy Hub",      Loader = function() return loadstring(game:HttpGet("https://FyyCommunity.my.id"))() end },
}

-- ============ SERVIÇOS ============
local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local CoreGui = game:GetService("CoreGui")
local TweenService = game:GetService("TweenService")
local Player = Players.LocalPlayer

pcall(function() if _G.Phzzx7Hub then _G.Phzzx7Hub:Destroy() end end)
pcall(function() if _G.Phzzx7Notify then _G.Phzzx7Notify:Destroy() end end)

local function novoGui(nome)
    local g = Instance.new("ScreenGui")
    g.Name = nome
    g.ResetOnSpawn = false
    g.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
    g.IgnoreGuiInset = true
    local ok = pcall(function() g.Parent = CoreGui end)
    if not ok then g.Parent = Player:WaitForChild("PlayerGui") end
    return g
end

local ScreenGui = novoGui("Phzzx7Hub")
_G.Phzzx7Hub = ScreenGui

local NotifyGui = novoGui("Phzzx7Notify")
_G.Phzzx7Notify = NotifyGui

-- ============ POSIÇÃO E TAMANHO (AJUSTE AQUI) ============
local LARGURA = 460          -- largura do painel
local ALTURA  = 300          -- altura do painel

local POS_X   = 0.5          -- 0.5 = centro horizontal
local POS_Y   = 0.55         -- ⬅️ 0.5 = centro, MAIOR = mais pra baixo
local OFF_X   = 0            -- ajuste fino horizontal (pixels)
local OFF_Y   = 0            -- ajuste fino vertical (pixels)

-- ============ FRAME PRINCIPAL ============
local MainFrame = Instance.new("Frame")
MainFrame.Name = "MainFrame"
MainFrame.Size = UDim2.new(0, LARGURA, 0, ALTURA)
MainFrame.Position = UDim2.new(POS_X, -LARGURA/2 + OFF_X, POS_Y, -ALTURA/2 + OFF_Y)
MainFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
MainFrame.BorderSizePixel = 0
MainFrame.Active = true
MainFrame.Draggable = true
MainFrame.Visible = true
MainFrame.Parent = ScreenGui

local MainCorner = Instance.new("UICorner")
MainCorner.CornerRadius = UDim.new(0, 10)
MainCorner.Parent = MainFrame

local MainStroke = Instance.new("UIStroke")
MainStroke.Color = Color3.fromRGB(255, 255, 255)
MainStroke.Thickness = 1.2
MainStroke.Transparency = 0.3
MainStroke.Parent = MainFrame

-- ============ BARRA DE TÍTULO ============
local TitleBar = Instance.new("Frame")
TitleBar.Size = UDim2.new(1, 0, 0, 32)
TitleBar.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
TitleBar.BorderSizePixel = 0
TitleBar.Parent = MainFrame

local TitleCorner = Instance.new("UICorner")
TitleCorner.CornerRadius = UDim.new(0, 10)
TitleCorner.Parent = TitleBar

local TitleCover = Instance.new("Frame")
TitleCover.Size = UDim2.new(1, 0, 0, 10)
TitleCover.Position = UDim2.new(0, 0, 1, -10)
TitleCover.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
TitleCover.BorderSizePixel = 0
TitleCover.Parent = TitleBar

local TitleLabel = Instance.new("TextLabel")
TitleLabel.Size = UDim2.new(1, -80, 1, 0)
TitleLabel.Position = UDim2.new(0, 12, 0, 0)
TitleLabel.BackgroundTransparency = 1
TitleLabel.Text = "🥚 PHZZX7 HUB"
TitleLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
TitleLabel.TextSize = 14
TitleLabel.Font = Enum.Font.GothamBold
TitleLabel.TextXAlignment = Enum.TextXAlignment.Left
TitleLabel.Parent = TitleBar

local CloseBtn = Instance.new("TextButton")
CloseBtn.Size = UDim2.new(0, 24, 0, 24)
CloseBtn.Position = UDim2.new(1, -30, 0, 4)
CloseBtn.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
CloseBtn.Text = "✕"
CloseBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
CloseBtn.TextSize = 13
CloseBtn.Font = Enum.Font.GothamBold
CloseBtn.BorderSizePixel = 0
CloseBtn.Parent = TitleBar

local CloseCorner = Instance.new("UICorner")
CloseCorner.CornerRadius = UDim.new(0, 6)
CloseCorner.Parent = CloseBtn

local MinBtn = Instance.new("TextButton")
MinBtn.Size = UDim2.new(0, 24, 0, 24)
MinBtn.Position = UDim2.new(1, -58, 0, 4)
MinBtn.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
MinBtn.Text = "—"
MinBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
MinBtn.TextSize = 13
MinBtn.Font = Enum.Font.GothamBold
MinBtn.BorderSizePixel = 0
MinBtn.Parent = TitleBar

local MinCorner = Instance.new("UICorner")
MinCorner.CornerRadius = UDim.new(0, 6)
MinCorner.Parent = MinBtn

-- ============ CONTAINER DE SCRIPTS (COM SCROLL) ============
local ScrollFrame = Instance.new("ScrollingFrame")
ScrollFrame.Size = UDim2.new(1, -20, 1, -50)
ScrollFrame.Position = UDim2.new(0, 10, 0, 42)
ScrollFrame.BackgroundTransparency = 1
ScrollFrame.BorderSizePixel = 0
ScrollFrame.ScrollBarThickness = 4
ScrollFrame.ScrollBarImageColor3 = Color3.fromRGB(255, 255, 255)
ScrollFrame.CanvasSize = UDim2.new(0, 0, 0, 0)
ScrollFrame.AutomaticCanvasSize = Enum.AutomaticSize.Y
ScrollFrame.Parent = MainFrame

local Grid = Instance.new("UIGridLayout")
Grid.CellSize = UDim2.new(0, 138, 0, 108)
Grid.CellPadding = UDim2.new(0, 10, 0, 10)
Grid.SortOrder = Enum.SortOrder.LayoutOrder
Grid.Parent = ScrollFrame

-- ============ NOTIFICAÇÃO ============
local NotifyFrame = Instance.new("Frame")
NotifyFrame.Size = UDim2.new(0, 300, 0, 42)
NotifyFrame.Position = UDim2.new(0.5, -150, 0.85, 0)
NotifyFrame.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
NotifyFrame.BorderSizePixel = 0
NotifyFrame.Visible = false
NotifyFrame.ZIndex = 10
NotifyFrame.Parent = NotifyGui

local NotifyCorner = Instance.new("UICorner")
NotifyCorner.CornerRadius = UDim.new(0, 8)
NotifyCorner.Parent = NotifyFrame

local NotifyStroke = Instance.new("UIStroke")
NotifyStroke.Color = Color3.fromRGB(255, 255, 255)
NotifyStroke.Thickness = 1
NotifyStroke.Parent = NotifyFrame

local NotifyLabel = Instance.new("TextLabel")
NotifyLabel.Size = UDim2.new(1, -20, 1, 0)
NotifyLabel.Position = UDim2.new(0, 10, 0, 0)
NotifyLabel.BackgroundTransparency = 1
NotifyLabel.Text = ""
NotifyLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
NotifyLabel.TextSize = 12
NotifyLabel.Font = Enum.Font.GothamMedium
NotifyLabel.TextWrapped = true
NotifyLabel.Parent = NotifyFrame

local notifyToken = 0
local function mostrarNotificacao(msg, tempo)
    notifyToken = notifyToken + 1
    local meuToken = notifyToken
    NotifyLabel.Text = msg
    NotifyFrame.Visible = true
    task.delay(tempo or 3, function()
        if notifyToken == meuToken then
            NotifyFrame.Visible = false
        end
    end)
end

-- ============ BOLINHA FLUTUANTE ============
local FloatingBtn = Instance.new("TextButton")
FloatingBtn.Size = UDim2.new(0, 50, 0, 50)
FloatingBtn.Position = UDim2.new(0, 15, 0.5, -25)
FloatingBtn.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
FloatingBtn.Text = "🥚"
FloatingBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
FloatingBtn.TextSize = 24
FloatingBtn.Font = Enum.Font.GothamBold
FloatingBtn.BorderSizePixel = 0
FloatingBtn.AutoButtonColor = false
FloatingBtn.Visible = false
FloatingBtn.Active = true
FloatingBtn.Draggable = true
FloatingBtn.Parent = ScreenGui

local FloatCorner = Instance.new("UICorner")
FloatCorner.CornerRadius = UDim.new(1, 0)
FloatCorner.Parent = FloatingBtn

local FloatStroke = Instance.new("UIStroke")
FloatStroke.Color = Color3.fromRGB(255, 255, 255)
FloatStroke.Thickness = 1.5
FloatStroke.Transparency = 0.3
FloatStroke.Parent = FloatingBtn

-- ============ CRIAR BOTÕES ============
local function criarBotao(scriptData, index)
    local Botao = Instance.new("TextButton")
    Botao.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
    Botao.Text = ""
    Botao.BorderSizePixel = 0
    Botao.AutoButtonColor = false
    Botao.LayoutOrder = index
    Botao.Parent = ScrollFrame

    local c = Instance.new("UICorner")
    c.CornerRadius = UDim.new(0, 8)
    c.Parent = Botao

    local s = Instance.new("UIStroke")
    s.Color = Color3.fromRGB(255, 255, 255)
    s.Thickness = 1
    s.Transparency = 0.5
    s.Parent = Botao

    local L = Instance.new("TextLabel")
    L.Size = UDim2.new(1, -8, 0, 24)
    L.Position = UDim2.new(0, 4, 0, 12)
    L.BackgroundTransparency = 1
    L.Text = scriptData.Nome
    L.TextColor3 = Color3.fromRGB(255, 255, 255)
    L.TextSize = 12
    L.Font = Enum.Font.GothamBold
    L.TextWrapped = true
    L.Parent = Botao

    local I = Instance.new("TextLabel")
    I.Size = UDim2.new(1, 0, 0, 20)
    I.Position = UDim2.new(0, 0, 0, 42)
    I.BackgroundTransparency = 1
    I.Text = "▶ EXECUTAR"
    I.TextColor3 = Color3.fromRGB(180, 180, 180)
    I.TextSize = 10
    I.Font = Enum.Font.GothamMedium
    I.Parent = Botao

    Botao.MouseEnter:Connect(function()
        TweenService:Create(Botao, TweenInfo.new(0.15), { BackgroundColor3 = Color3.fromRGB(35, 35, 35) }):Play()
        TweenService:Create(s, TweenInfo.new(0.15), { Transparency = 0 }):Play()
        TweenService:Create(I, TweenInfo.new(0.15), { TextColor3 = Color3.fromRGB(255, 255, 255) }):Play()
    end)

    Botao.MouseLeave:Connect(function()
        TweenService:Create(Botao, TweenInfo.new(0.15), { BackgroundColor3 = Color3.fromRGB(20, 20, 20) }):Play()
        TweenService:Create(s, TweenInfo.new(0.15), { Transparency = 0.5 }):Play()
        TweenService:Create(I, TweenInfo.new(0.15), { TextColor3 = Color3.fromRGB(180, 180, 180) }):Play()
    end)

    Botao.MouseButton1Click:Connect(function()
        mostrarNotificacao("Executando " .. scriptData.Nome .. "...", 2)
        local ok, err = pcall(scriptData.Loader)
        if ok then
            mostrarNotificacao("✅ " .. scriptData.Nome .. " executado!", 3)
        else
            mostrarNotificacao("❌ Erro: " .. tostring(err), 4)
            warn("[Phzzx7 Hub] " .. tostring(err))
        end
    end)

    return Botao
end

for i, sd in ipairs(SCRIPTS) do
    criarBotao(sd, i)
end

-- ============ POSIÇÃO ABERTA E FECHADA ============
local POSICAO_ABERTA  = UDim2.new(POS_X, -LARGURA/2 + OFF_X, POS_Y, -ALTURA/2 + OFF_Y)
local POSICAO_FECHADA = UDim2.new(POS_X, -LARGURA/2 + OFF_X, 1.5, 0)

local aberto = true

local function esconderHub()
    aberto = false
    MainFrame:TweenPosition(
        POSICAO_FECHADA,
        Enum.EasingDirection.In, Enum.EasingStyle.Quad, 0.25, true,
        function()
            MainFrame.Visible = false
            FloatingBtn.Visible = true
        end
    )
end

local function mostrarHub()
    aberto = true
    FloatingBtn.Visible = false
    MainFrame.Visible = true
    MainFrame.Position = POSICAO_FECHADA
    MainFrame:TweenPosition(
        POSICAO_ABERTA,
        Enum.EasingDirection.Out, Enum.EasingStyle.Quad, 0.25, true
    )
end

local function toggleGui()
    if aberto then
        esconderHub()
        mostrarNotificacao("Hub escondido! Clique no 🥚 ou aperte RightControl", 3)
    else
        mostrarHub()
    end
end

CloseBtn.MouseButton1Click:Connect(toggleGui)
MinBtn.MouseButton1Click:Connect(toggleGui)
FloatingBtn.MouseButton1Click:Connect(toggleGui)

UserInputService.InputBegan:Connect(function(input, gp)
    if gp then return end
    if input.KeyCode == TOGGLE_KEY then
        toggleGui()
    end
end)

mostrarNotificacao("Phzzx7 Hub carregado! RightControl para abrir/fechar", 4)
print("[Phzzx7 Hub] Carregado. Posição Y = " .. POS_Y)
