-- wordfight




















local function getMethodLoading()
	local GG = (getgenv and getgenv()) or _G or shared;
	if GG.IdenG ~= nil then
		Iden = GG.IdenG
	else
		pcall(function() Iden = identifyexecutor(); end);
	end;
	if game:GetService("CoreGui"):FindFirstChild("InputPcToMobile") then
		pcall(function() game:GetService("CoreGui"):FindFirstChild("InputPcToMobile"):Destroy(); end);
	end;
	if not game:GetService("CoreGui"):FindFirstChild("Neu") then
		local Neu = Instance.new("ScreenGui");
		Neu.Parent = game:GetService("CoreGui")
		Neu.IgnoreGuiInset = true;
		GG["Neu"] = Neu;
	end;

	GG["DisableSystem"] = true;

	local Configs = {
		["Stats"] = {
			["Melee"] = false;
			["Defense"] = false;
			["Sword"] = false;
			["Gun"] = false;
			["BloxFruit"] = false;
			["Points"] = 2
		};
		["Farming"] = {
			["Weapon"] = "Combat";
			["Level"] = {
				["AutoFarm"] = false;
				["AutoSea2"] = true;
				["AutoSea3"] = true;
				["TP_Speed"] = 2;
			};
			["Sea1"] = {
				["AutoSaber"] = false;
				["AutoSaberQuest"] = false;
				["Hop"] = false;
				["AutoSaw"] = false;
				["HopSaw"] = false;
			};
			["Sea2"] = {
				["AutoFactory"] = false;
				["AutoEctoplasm"] = false;
				["AutoBartilo"] = false;
			};
			["Sea3"] = {
				["AutoKillDoughKing"] = false;
				["AutoCastleRaid"] = false;
				["AutoElitehunter"] = false;
				["AutoFarmBone"] = false;
				["AutoSpawnCakePrince"] = false;
				["AutoCakePrince"] = false;
				["AutoFarmCakePrince"] = false;
				["AutoBuddySword"] = false;
				["AutoCarvender"] = false;
				["AutoCarvenderHop"] = false;
				["ArenaTrainer"] = false;
			};
			["AllSea"] = {
				["AutoHopSea"] = true;
				["AutoHopServer"] = false;
				["Melee"] = {
					["DeathStep"] = false;
					["SharkmanKarate"] = false;
				};
			};
		};
		["SeaEvents"] = {
			["Target"] = {
				["Shark"] = false;
				["Terrorshark"] = false;
				["Piranha"] = false;
				["FishCrewMember"] = false;
			};
			["TP_Speed"] = 3.5;
		};
		["Players"] = {
			["Client"] = {
				["AntiAFK"] = true;
				["Float"] = false;
				["Noclip"] = false;
				["FlySpeed"] = 1;
				["Fly"] = false;
				["DMGAura"] = false;
				["InfiniteEnergy"] = false;
				["AutoBusoHaki"] = true;
				["AutoOBVHaki"] = false;
				["WalkOnWater"] = false;
				["WalkSpeed"] = 1;
				["WalkSpeedToggle"] = false;
				["JumpPower"] = 50;
				["JumpPowerToggle"] = false;
				["MaxFPSCap"] = 60;
				["NoRender"] = false;
				["BlackScreen"] = false;
			};
			["Combat"] = {
				["Target"] = nil;
				["Spectate"] = false;
				["AutoKillTarget"] = false;
				["Aimbot"] = false;
				["SilentAim"] = false;
				["AutoBounty"] = false;
			};
			["Visual"] = {
				["HideDamageText"] = false;
				["HideNotifications"] = false;
				["HideChat"] = false;
				["HideLeaderboard"] = false;
			};
		};
		["Raid"] = {
			["Manual"] = {
				["SelectRaid"] = "Dark";
				["KillAura"] = false;
				["TeleportToNextIsland"] = false;
			};
		};
		["Teleport"] = {
			["Island"] = {
				["Target"] = nil;
			};
			["NPCs"] = {
				["Target"] = nil;
			};
			["Player"] = {
				["Target"] = nil;
			};
			["Mob_Boss"] = {
				["Target"] = nil;
			};
			["TP_Speed"] = 2;
			["TP_Bypass"] = false;
		};
		["Shop"] = {
			["AutoBuyLegendarySword"] = false;
			["AutoBuyHakiColor"] = false;
		};
		["ESP"] = {
			["Flower"] = false;
			["Fruits"] = false;
			["Players"] = false;
			["Chests"] = false;
			["IslandESP"] = false;
			["Mirage"] = false;
			["AdvancedFD"] = false;
			["RealFruits"] = false;
			["Gear"] = false;
			["S3W2"] = false; -- Don't touch if you don't know what is it
		};
		["Server"] = {
			["AutoExec"] = true;
		};
		["Settings"] = {
			["UI"] = {
				["Fly"] = {
					["Show_Hide"] = false;
					["Up_Down"] = false;
					["Big_Small"] = false;
				};
			};
			["System"] = {
				["ClientDebug"] = false;
				["Commands"] = false;
			};
			["AutoFarm"] = {
				["Hitbox"] = false;
				["BringMob"] = false;
				["BringMobType"] = "Target";
				["BringMobDistance"] = 180;
				["Stackable"] = true; -- ALWAYS ON ⚠⚠⚠
				["PosX"] = 0;
				["PosY"] = 19;
				["PosZ"] = -10;
				["TP_Speed"] = 2;
			};
			["AutoRaid"] = {
				["PosX"] = 0;
				["PosY"] = 0;
				["PosZ"] = 0;
				["TP_Speed"] = 2;
			};
			["AutoBounty"] = {
				["PosX"] = 0;
				["PosY"] = 19;
				["PosZ"] = -10;
				["TP_Speed"] = 2;
			};
			["AutoChest"] = {
				["Detail"] = true;
				["Normal"] = true;
				["Fragment"] = true;
				["TP_Speed"] = 2
			};
			["Game"] = {
				["Gravity"] = 192;
				["Lighting_Tech"] = "ShadowMap";
			};
		};
		["System"] = {
			["WebhookLive"] = "";
			["WebhookRequest"] = "";
			["BREAKALLTHISSHITHAHAHAHAHA"] = false;
			["Selected_Boss"] = {
				["Obj"] = nil; ["Auto"] = false;
			};
			["Selected_Mob"] = {
				["Obj"] = nil; ["Auto"] = false;
			};
			["Selected_Material"] = {
				["Obj"] = nil; ["Auto"] = false;
			};
			["Astaootslai"] = false;
			["Backpack"] = {};
			["AutoRaid"] = false;
			["AutoChest"] = false;
			["SelectedShip"] = nil;
		};
	};

	local PData = {
		["Melee"] = {
			["BlackLeg"]= {
				["Have"] = false;
				["Level"] = 0;
			};
			["DeathStep"] = {
				["Have"] = false;
				["Level"] = 0;
				["Step2"] = false;
			};
			["FishmanKarate"] = {
				["Have"] = false;
				["Level"] = 0;
			};
			["SharkmanKarate"] = {
				["Have"] = false;
				["Level"] = 0;
				["Step2"] = false;
			};
		};
		["DidBartilo"] = false;
	};

	local VirtualInputManager = game:GetService('VirtualInputManager');
	local W = game:GetService("Workspace");
	local P = game:GetService("Players");
	local L = game:GetService("Lighting");
	local C = game:GetService("CoreGui");
	local H = game:GetService("RunService");
	local R = game:GetService("ReplicatedStorage");
	local VU = game:GetService("VirtualUser");
	local T = game:GetService("TeleportService");
	local CommF = R.Remotes.CommF_;
	local selff = P.LocalPlayer;
	local PSG = selff:WaitForChild("PlayerGui");
	local Data = selff.Data;
	local NPCs = W:WaitForChild("NPCs", 10);
	local Enemy = W:WaitForChild("Enemies", 10);
	local Backpack = selff.Backpack;
	local Neu = GG["Neu"];
	local Enem = {};
	local Chars = {};
	local CollectionService = game:GetService("CollectionService");
	local selc = selff.Character;
	local Cam = W:WaitForChild("Camera");
	local IgnoreE = false;
	if GG and GG.ActiveTime == nil then
		GG.ActiveTime = 0;
	end;
	if GG.FullAutoAzureEmber == nil then
		GG.FullAutoAzureEmber = true;
	end;
	Lib = nil;

	setc = setclipboard or toclipboard;
	tos = tostring;
	tablein = table.insert;
	tablecl = table.clear;
	print = print;
	tk = task;
	tspawn = tk.spawn;
	twait = tk.wait;
	tdelay = task.delay;
	wait = wait;
	FindFirstChild = game.FindFirstChild;
	Vec3 = Vector3.new;
	CF = CFrame.new;
	str = string;
	strgsub = str.gsub;
	strfind = str.find;
	pir = pairs;
	IsA = game.IsA;
	pcal = pcall;
	FindFirstChildOfClass = game.FindFirstChildOfClass;
	GetAttribute = game.GetAttribute;
	SetAttribute = game.SetAttribute;
	Instancen = Instance.new;
	tick = tick;
	delay = delay;
	SetPrimaryPartCFrame = W.SetPrimaryPartCFrame;
	GetPivot = W.GetPivot;
	GetChildren = game.GetChildren;
	GetDescendants = game.GetDescendants;
	FindFirstChildWhichIsA = game.FindFirstChildWhichIsA;
	mfloor = math.floor

	local NothingLibrary = loadstring(game:HttpGet('https://raw.githubusercontent.com/3345-c-a-t-s-u-s/neuron/refs/heads/main/script.lua'))();
	local Notification = NothingLibrary.Notification();

	local CONTROL = {F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0};

	FLYING = false;

	speedofthevfly = 1;

	speedofthefly = 1;

	local cmdm = selff:GetMouse();

	local screenGui2 = Instancen("ScreenGui"); screenGui2.Parent = game:GetService("CoreGui"); screenGui2.Name = "InputPcToMobile"; local buttonSize = UDim2.new(0.05, 0, 0.05, 0);

	local function createButton(key, position) local button = Instancen("TextButton"); button.Parent = screenGui2;
		button.Name = key; button.Text = key; button.Size = buttonSize; button.Position = position; button.BackgroundColor3 = Color3.new(0.5, 0.5, 0.5); local isPressed = false;
		button.MouseButton1Down:Connect(function() isPressed = true; if key == "W" then CONTROL.F = speedofthefly; elseif key == "S" then CONTROL.B = -speedofthefly; elseif key == "A" then CONTROL.L = -speedofthefly; elseif key == "D" then CONTROL.R = speedofthefly end; end);
		button.MouseButton1Up:Connect(function() isPressed = false; if key == "W" then CONTROL.F = 0; elseif key == "S" then CONTROL.B = 0; elseif key == "A" then CONTROL.L = 0; elseif key == "D" then CONTROL.R = 0; end; end);
	end;

	createButton("W", UDim2.new(0.05, 0, 0.1, 0));createButton("A", UDim2.new(0, 0, 0.2, 0));createButton("S", UDim2.new(0.05, 0, 0.3, 0));createButton("D", UDim2.new(0.1, 0, 0.2, 0));
	TTJYMobileIn = game:GetService("CoreGui"):WaitForChild("InputPcToMobile");

	JKLL, JKLLJ = pcall(function() require(R.Util.CameraShaker):Stop() end);

	placeId = game.PlaceId
	WorldCheck = {["First Sea"]=false,["Second Sea"]=false,["Third Sea"]=false}
	if placeId == 2753915549 then
		WorldCheck["First Sea"] = true;
	elseif placeId == 4442272183 then
		WorldCheck["Second Sea"] = true;
	elseif placeId == 7449423635 then
		WorldCheck["Third Sea"] = true;
	end;

	GG["DisableSystem"] = false;

	if WorldCheck["First Sea"] then
		BossList = {
			"The Gorilla King",
			"Bobby",
			"Yeti",
			"Mob Leader",
			"Vice Admiral",
			"Warden",
			"Chief Warden",
			"Swan",
			"Magma Admiral",
			"Fishman Lord",
			"Wysper",
			"Thunder God",
			"Cyborg",
			"Saber Expert"
		};
	elseif WorldCheck["Second Sea"] then
		BossList = {
			"Diamond",
			"Jeremy",
			"Fajita",
			"Don Swan",
			"Smoke Admiral",
			"Cursed Captain",
			"Darkbeard",
			"Order",
			"Awakened Ice Admiral",
			"Tide Keeper"
		};
	elseif WorldCheck["Third Sea"] then
		BossList = {
			"Stone",
			"Island Empress",
			"Kilo Admiral",
			"Captain Elephant",
			"Beautiful Pirate",
			"rip_indra True Form",
			"Longma",
			"Soul Reaper",
			"Cake Queen"
		};
	end;

	if WorldCheck["First Sea"] then
		MobList = {
			"Bandit",
			"Monkey",
			"Gorilla",
			"Pirate",
			"Brute",
			"Desert Bandit",
			"Desert Officer",
			"Snow Bandit",
			"Snowman",
			"Chief Petty Officer",
			"Sky Bandit",
			"Dark Master",
			"Toga Warrior",
			"Gladiator",
			"Military Soldier",
			"Military Spy",
			"Fishman Warrior",
			"Fishman Commando",
			"God's Guard",
			"Shanda",
			"Royal Squad",
			"Royal Soldier",
			"Galley Pirate",
			"Galley Captain"
		};
	elseif WorldCheck["Second Sea"] then
		MobList = {
			"Raider",
			"Mercenary",
			"Swan Pirate",
			"Factory Staff",
			"Marine Lieutenant",
			"Marine Captain",
			"Zombie",
			"Vampire",
			"Snow Trooper",
			"Winter Warrior",
			"Lab Subordinate",
			"Horned Warrior",
			"Magma Ninja",
			"Lava Pirate",
			"Ship Deckhand",
			"Ship Engineer",
			"Ship Steward",
			"Ship Officer",
			"Arctic Warrior",
			"Snow Lurker",
			"Sea Soldier",
			"Water Fighter"
		};
	elseif WorldCheck["Third Sea"] then
		MobList = {
			"Pirate Millionaire",
			"Dragon Crew Warrior",
			"Dragon Crew Archer",
			"Female Islander",
			"Giant Islander",
			"Marine Commodore",
			"Marine Rear Admiral",
			"Fishman Raider",
			"Fishman Captain",
			"Forest Pirate",
			"Mythological Pirate",
			"Jungle Pirate",
			"Musketeer Pirate",
			"Reborn Skeleton",
			"Living Zombie",
			"Demonic Soul",
			"Posessed Mummy",
			"Peanut Scout",
			"Peanut President",
			"Ice Cream Chef",
			"Ice Cream Commander",
			"Cookie Crafter",
			"Cake Guard",
			"Baking Staff",
			"Head Baker",
			"Cocoa Warrior",
			"Chocolate Bar Battler",
			"Sweet Thief",
			"Candy Rebel",
			"Candy Pirate",
			"Snow Demon",
			"Isle Outlaw",
			"Island Boy",
			"Sun-kissed Warrior",
			"Isle Champion"
		};
	end;

	function SendWeb(a, b)
		request({
			Url = a,
			Headers = {['Content-Type'] = 'application/json',},
			Method = 'POST',
			Body = game:GetService('HttpService'):JSONEncode({
				content = b;
			});
		});
	end;function tableTostring(t, indent)
		indent = indent or 0;
		local str = "{\n";
		local indentStr = string.rep("    ", indent);

		for key, value in pairs(t) do
			local keyStr = "";
			if type(key) == "string" then
				keyStr = '["' .. key .. '"] = ';
			elseif type(key) == "number" then
				keyStr = "[" .. key .. "] = ";
			end;

			if type(value) == "table" then
				str = str .. indentStr .. keyStr .. tableTostring(value, indent + 1) .. ",\n";
			else
				str = str .. indentStr .. keyStr .. tostring(value) .. ",\n";
			end;
		end;

		str = str .. string.rep("    ", indent - 1) .. "}";
		return str;
	end;

	function AutoExec()

	end;

	function RepText(obj, num, text)
		local newText = strgsub(text, ('.'):rep(num), function(a)
			return a;
		end);
		local awdadaAA = obj:NewTitle(newText)
		return awdadaAA;
	end;

	function dist(position)
		return selff:DistanceFromCharacter(position);
	end;function Tp2(xyz)
		if FindFirstChild(selff.Character, "HumanoidRootPart") then
			selff.Character.HumanoidRootPart.CFrame = xyz;
		end;
	end;function Tp(a, b, c, speedoftpNTP, obj)
		KLLOP = selff.Character.HumanoidRootPart;
		pKLLOP = KLLOP.Position;
		cpKLLOP = Vec3(pKLLOP.x, pKLLOP.y, pKLLOP.z);
		tpKLOOP, sdKLOOp, saveAlKLOOP, svetarKLLOP = nil
		if typeof(a) == "number" then
			tpKLOOP = Vec3(a, b, c); sdKLOOp = speedoftpNTP;
			saveAlKLOOP = CF(a, b, c);
			svetarKLLOP = CF(a, b, c);
		elseif typeof(a) == "CFrame" then
			tpKLOOP = a.Position; sdKLOOp = b;
			saveAlKLOOP = a
			svetarKLLOP = a
		end;
		typeofValidInstances = nil;
		if typeof(c) == "Instance" then
			FollowValidInstances = true;
			typeofValidInstances = c;
		else
			if typeof(obj) == "Instance" then
				FollowValidInstances = true;
				typeofValidInstances = obj;
			else
				FollowValidInstances = false;
			end;
		end;
		dtnKLOOP = (tpKLOOP - cpKLLOP).Unit;
		dceKLLOP = (tpKLOOP - cpKLLOP).Magnitude;
		ssKLLOP = mfloor(dceKLLOP / sdKLOOp);
		if not FindFirstChild(selff.Character, "Humanoid") then
			repeat twait(1); until FindFirstChild(selff.Character, "Humanoid") and FindFirstChild(selff.Character, "HumanoidRootPart") twait(1);
			KLLOP = selff.Character.HumanoidRootPart
			pKLLOP = KLLOP.Position;
		end;
		if FindFirstChild(selff.Character, "Humanoid") and selff.Character.Humanoid.Health <= 0 then
			repeat twait(1); until FindFirstChild(selff.Character, "Humanoid") and FindFirstChild(selff.Character, "HumanoidRootPart") and selff.Character.Humanoid.Health > 0 twait(1);
			KLLOP = selff.Character.HumanoidRootPart
			pKLLOP = KLLOP.Position;
		end;
		if not FollowValidInstances then
			for i = 1, ssKLLOP do
				if Configs.System.BREAKALLTHISSHITHAHAHAHAHA then break; end;
				if dist(saveAlKLOOP.Position) <= 50 then Tp2(svetarKLLOP); break; end;
				cpKLLOP = cpKLLOP + dtnKLOOP * sdKLOOp;
				selff.Character.HumanoidRootPart.CFrame = CF(cpKLLOP);
				twait();
			end;
		else
			pcal(function()
				for i = 1, ssKLLOP do
					tpKLOOP = typeofValidInstances.Position;
					dtnKLOOP = (tpKLOOP - cpKLLOP).Unit;
					dceKLLOP = (tpKLOOP - cpKLLOP).Magnitude;
					ssKLLOP = mfloor(dceKLLOP / sdKLOOp);
					cpKLLOP = cpKLLOP + dtnKLOOP * sdKLOOp;
					if Configs.System.BREAKALLTHISSHITHAHAHAHAHA then break; end;
					if dist(typeofValidInstances.Position) <= 50 then Tp2(tpKLOOP); break; end;
					selff.Character.HumanoidRootPart.CFrame = CF(cpKLLOP);
					twait();
				end;
			end);
		end;
	end;function TpBypass(a)
		if Configs.Teleport.TP_Bypass then
			if typeof(a) == "CFrame" and selc then
				SetPrimaryPartCFrame(selc, a)
				wait();
				selc.Humanoid.Health = 0;
				repeat twait() until selc and selc.Humanoid
				SetPrimaryPartCFrame(selc, a)
				SetPrimaryPartCFrame(selc, a)
				SetPrimaryPartCFrame(selc, a)
			end;
		end; wait(0.7)
		repeat twait(1); until FindFirstChild(selff.Character, "Humanoid") and selff.Character.Humanoid.Health > 0
	end;function tpwithseat(xyz,speedoftpNTP)
		guyejrigrjerhjfcnwhfwefji = selff.Character.HumanoidRootPart;
		reuifrefiremfvuhuevr = guyejrigrjerhjfcnwhfwefji.Position;
		HHAHDAWUDnenfsfewuhfefwfowife = Vec3(reuifrefiremfvuhuevr.x, reuifrefiremfvuhuevr.y, reuifrefiremfvuhuevr.z);
		SDFGHJKWDuewuewfjewjfuew = xyz.Position;
	
		HDNwajdiir3jiwisjdjifew = (SDFGHJKWDuewuewfjewjfuew - HHAHDAWUDnenfsfewuhfefwfowife).Unit;
		wjjdjiwjidwjiwejiewifjwijweifoj = (SDFGHJKWDuewuewfjewjfuew - HHAHDAWUDnenfsfewuhfefwfowife).Magnitude;
		ajakdapujupyjlyljyujyupjpuy = mfloor(wjjdjiwjidwjiwejiewifjwijweifoj / speedoftpNTP);
		if not FindFirstChild(selff.Character, "Humanoid") then
			repeat twait(1.867); until FindFirstChild(selff.Character, "Humanoid")
		end;
		for i = 1, ajakdapujupyjlyljyujyupjpuy do
			if Configs.System.BREAKALLTHISSHITHAHAHAHAHA then break; end;
			HHAHDAWUDnenfsfewuhfefwfowife = HHAHDAWUDnenfsfewuhfefwfowife + HDNwajdiir3jiwisjdjifew * speedoftpNTP;
			selff.Character.Humanoid.SeatPart.Parent:SetPrimaryPartCFrame(CF(HHAHDAWUDnenfsfewuhfefwfowife));
			twait();
		end;
	end;function BP()
		Configs.System.Backpack = Backpack:GetChildren();
		return Backpack:GetChildren();
	end;function SetHum(obj)
		obj.HumanoidRootPart.CanCollide = false; obj.Humanoid.WalkSpeed = 0; obj.Head.CanCollide = false;
		obj.HumanoidRootPart.CanQuery = false;
		if Configs.Settings.AutoFarm.Hitbox then
			obj.HumanoidRootPart.Size = Vec3(64, 64, 64);
		end;
		if FindFirstChild(obj, "Humanoid") then
			obj.Humanoid.WalkSpeed = 0;
			if FindFirstChild(obj.Humanoid, "Animator") then
				obj.Humanoid.Animator:Destroy();
			end;
		end;
		if FindFirstChild(obj, "Busy") then
			obj.Busy.Value = true;
		end;
		if FindFirstChild(obj, "Stun") then
			obj.Stun.Value = 1;
		end;
	end;function getInventory(value, types)
		if FindFirstChild(Backpack, value) then
			if types == "Check" then return true; end;
		elseif FindFirstChild(selff.Character, value) then
			if types == "Check" then return true; end;
		else
			for i, v in pairs(CommF:InvokeServer("getInventory")) do
				if type(v) == "table" then
					if types == "Check" and value == v.Name then
						return true
					elseif types == "Count" then
						return v.Count
					elseif types == "MaxCount" then
						return v.MaxCount
					end;
				end;
			end;
		end;
		return false;
	end;

	function EquipWeapon(Name)
		if FindFirstChild(Backpack, Name) then
			ToolJKNLL = FindFirstChild(Backpack, Name);
			twait(0.02);
			selc.Humanoid:EquipTool(ToolJKNLL);
			twait(0.5);
		end;
	end;

	function InfStamina()
		if selc and selc.Parent then
			selc.Energy.Value = selc.Energy.MaxValue;
		end;
	end;

	function AutoChest(bool)
		ProcessAutoChest = bool;
		if Configs.Settings.AutoChest.Normal and not Configs.Settings.AutoChest.Detail then
			shdtts = math.huge; nearestChest = nil;
			for _, v in pir(W:GetChildren()) do
				if IsA(v, "BasePart") and (v.Name == "Chest1" or v.Name == "Chest2" or v.Name == "Chest3" or v.Name == "FragChest") then
					if dist(v.Position) < shdtts then 
						nearestChest = v; shdtts = dist(v.Position) 
					end; 
				end; 
			end;
		elseif (Configs.Settings.AutoChest.Normal and Configs.Settings.AutoChest.Detail) or (not Configs.Settings.AutoChest.Normal and Configs.Settings.AutoChest.Detail) then
			shdtts = math.huge; nearestChest = nil;
			for _, v in pir(W:GetDescendants()) do
				if IsA(v, "BasePart") and (v.Name == "Chest1" or v.Name == "Chest2" or v.Name == "Chest3" or v.Name == "FragChest") then
					if dist(v.Position) < shdtts then
						nearestChest = v; shdtts = dist(v.Position); 
					end; 
				end; 
			end; 
		end;
		if nearestChest ~= nil then
			Tp(nearestChest.Position.X, nearestChest.Position.Y, nearestChest.Position.Z, Configs.Settings.AutoChest.TP_Speed); twait();
			Tp2(CF(nearestChest.Position.X, nearestChest.Position.Y, nearestChest.Position.Z)); twait(1);
		end;
		ProcessAutoChest = false;
	end;

	DamageAura = true;
	Fast = false;
	NeedAttacking = false;
	if JKLL then
		getHits = function(Size)
			local Hits = {};
			if nearbymon then
				for i=1,#Enem do local v = Enem[i];
					local Human = FindFirstChildOfClass(v, "Humanoid");
					if Human and Human.Root
