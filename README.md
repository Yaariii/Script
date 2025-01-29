wait(1)
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

local attentionLabel = Instance.new("TextLabel")
attentionLabel.Parent = ScreenGui
attentionLabel.Size = UDim2.new(1, 0, 0.05, 0)
attentionLabel.Position = UDim2.new(0, 0, -0.1, 0)
attentionLabel.BackgroundTransparency = 1
attentionLabel.TextScaled = true
attentionLabel.RichText = true
attentionLabel.TextStrokeTransparency = 0
attentionLabel.Text = "<font color='#FFFFFF'>The event has end!</font>"

local TweenService = game:GetService("TweenService")
local tweenInfo = TweenInfo.new(.7, Enum.EasingStyle.Cubic, Enum.EasingDirection.Out)
local targetPosition = UDim2.new(0, 0, 0.05, 0)
local attentionTween = TweenService:Create(attentionLabel, tweenInfo, {Position = targetPosition})

attentionTween:Play()
attentionTween.Completed:Wait()
wait(5)
local TextLabel = Instance.new("TextLabel")
TextLabel.Parent = ScreenGui
TextLabel.Size = UDim2.new(1, 0, 0.05, 0)
TextLabel.Position = UDim2.new(0, 0, -1, 0)
TextLabel.BackgroundTransparency = 1
TextLabel.TextScaled = true
TextLabel.RichText = true
TextLabel.TextStrokeTransparency = 0

local message = "<font color='#00FF00'>Blox Fruit Gacha</font> was back..."
TextLabel.Text = "<font color='#FFFFFF'>"..message.."</font>"

local targetPositionMain = UDim2.new(0, 0, .1, 0)
local textTween = TweenService:Create(TextLabel, tweenInfo, {Position = targetPositionMain})

textTween:Play()
textTween.Completed:Wait()

wait(5)

local direction = math.random(1, 2)
local exitTarget = UDim2.new(direction == 1 and -1 or 1, 0, .1, 0)
local exitTargetAttention = UDim2.new(direction == 1 and -1 or 1, 0, 0.05, 0)
local exitTweenMain = TweenService:Create(TextLabel, tweenInfo, {Position = exitTarget})
local exitTweenAttention = TweenService:Create(attentionLabel, tweenInfo, {Position = exitTargetAttention})

exitTweenMain:Play()
exitTweenAttention:Play()
exitTweenMain.Completed:Wait()
exitTweenAttention.Completed:Wait()

TextLabel:Destroy()
attentionLabel:Destroy()
