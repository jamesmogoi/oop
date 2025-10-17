-- Pull in the wezterm API
local wezterm = require("wezterm")

-- This will hold the configuration.
local config = wezterm.config_builder()

-- ===== FIX FOR FLICKERING AND WINDOW CONTROLS =====
-- Use XWayland instead of native Wayland to fix buffer scaling issues
config.enable_wayland = false

-- ===== FONT CONFIGURATION =====
config.font = wezterm.font("JetBrainsMono Nerd Font")
config.font_size = 14
config.line_height = 1.2

-- Enable font ligatures for better code readability
config.harfbuzz_features = { 'calt=1', 'clig=1', 'liga=1' }

-- ===== WINDOW APPEARANCE =====
config.window_decorations = "TITLE | RESIZE"
config.window_background_opacity = 0.8
config.text_background_opacity = 1.0

-- Add padding for breathing room
config.window_padding = {
  left = 12,
  right = 12,
  top = 12,
  bottom = 12,
}

-- ===== TAB BAR =====
config.enable_tab_bar = true
config.hide_tab_bar_if_only_one_tab = false
config.use_fancy_tab_bar = false
config.tab_bar_at_bottom = false
config.tab_max_width = 32
config.show_tab_index_in_tab_bar = true

-- ===== COLOR SCHEME =====
-- Your custom coolnight theme
config.colors = {
  foreground = "#CBE0F0",
  background = "#011423",
  cursor_bg = "#47FF9C",
  cursor_border = "#47FF9C",
  cursor_fg = "#011423",
  selection_bg = "#033259",
  selection_fg = "#CBE0F0",
  
  ansi = {
    "#214969", -- black
    "#E52E2E", -- red
    "#44FFB1", -- green
    "#FFE073", -- yellow
    "#0FC5ED", -- blue
    "#a277ff", -- magenta
    "#24EAF7", -- cyan
    "#24EAF7", -- white
  },
  
  brights = {
    "#214969", -- bright black
    "#E52E2E", -- bright red
    "#44FFB1", -- bright green
    "#FFE073", -- bright yellow
    "#A277FF", -- bright blue
    "#a277ff", -- bright magenta
    "#24EAF7", -- bright cyan
    "#24EAF7", -- bright white
  },
  
  tab_bar = {
    background = "#011423",
    active_tab = {
      bg_color = "#0FC5ED",
      fg_color = "#011423",
      intensity = "Bold",
    },
    inactive_tab = {
      bg_color = "#033259",
      fg_color = "#CBE0F0",
    },
    inactive_tab_hover = {
      bg_color = "#214969",
      fg_color = "#CBE0F0",
    },
    new_tab = {
      bg_color = "#033259",
      fg_color = "#CBE0F0",
    },
    new_tab_hover = {
      bg_color = "#214969",
      fg_color = "#CBE0F0",
    },
  },
}

-- ===== CURSOR =====
config.default_cursor_style = "BlinkingBar"
config.cursor_blink_rate = 500

-- ===== SCROLLBACK =====
config.scrollback_lines = 10000
config.enable_scroll_bar = false

-- ===== PERFORMANCE =====
config.animation_fps = 60
config.max_fps = 60
config.front_end = "OpenGL"

-- ===== BELL =====
config.audible_bell = "Disabled"

-- ===== SMART FEATURES =====
config.automatically_reload_config = true
config.window_close_confirmation = "NeverPrompt"

-- ===== KEYBINDINGS =====
local act = wezterm.action

config.keys = {
  -- Split panes (using CTRL+SHIFT)
  { key = "d", mods = "CTRL|SHIFT", action = act.SplitHorizontal { domain = "CurrentPaneDomain" } },
  { key = "D", mods = "CTRL|SHIFT", action = act.SplitVertical { domain = "CurrentPaneDomain" } },
  
  -- Navigate panes (using ALT)
  { key = "h", mods = "ALT", action = act.ActivatePaneDirection("Left") },
  { key = "l", mods = "ALT", action = act.ActivatePaneDirection("Right") },
  { key = "k", mods = "ALT", action = act.ActivatePaneDirection("Up") },
  { key = "j", mods = "ALT", action = act.ActivatePaneDirection("Down") },
  
  -- Close pane
  { key = "w", mods = "CTRL|SHIFT", action = act.CloseCurrentPane { confirm = true } },
  
  -- Zoom pane
  { key = "z", mods = "CTRL|SHIFT", action = act.TogglePaneZoomState },
  
  -- Tab management (using CTRL)
  { key = "t", mods = "CTRL|SHIFT", action = act.SpawnTab("CurrentPaneDomain") },
  { key = "w", mods = "CTRL|ALT", action = act.CloseCurrentTab { confirm = true } },
  
  -- Navigate tabs
  { key = "Tab", mods = "CTRL", action = act.ActivateTabRelative(1) },
  { key = "Tab", mods = "CTRL|SHIFT", action = act.ActivateTabRelative(-1) },
  
  -- Quick tab selection (ALT+number)
  { key = "1", mods = "ALT", action = act.ActivateTab(0) },
  { key = "2", mods = "ALT", action = act.ActivateTab(1) },
  { key = "3", mods = "ALT", action = act.ActivateTab(2) },
  { key = "4", mods = "ALT", action = act.ActivateTab(3) },
  { key = "5", mods = "ALT", action = act.ActivateTab(4) },
  { key = "6", mods = "ALT", action = act.ActivateTab(5) },
  { key = "7", mods = "ALT", action = act.ActivateTab(6) },
  { key = "8", mods = "ALT", action = act.ActivateTab(7) },
  { key = "9", mods = "ALT", action = act.ActivateTab(8) },
  
  -- Search
  { key = "f", mods = "CTRL|SHIFT", action = act.Search("CurrentSelectionOrEmptyString") },
  
  -- Copy/Paste (standard Linux shortcuts)
  { key = "c", mods = "CTRL|SHIFT", action = act.CopyTo("Clipboard") },
  { key = "v", mods = "CTRL|SHIFT", action = act.PasteFrom("Clipboard") },
  
  -- Font size
  { key = "=", mods = "CTRL", action = act.IncreaseFontSize },
  { key = "-", mods = "CTRL", action = act.DecreaseFontSize },
  { key = "0", mods = "CTRL", action = act.ResetFontSize },
  
  -- Reload config
  { key = "r", mods = "CTRL|SHIFT", action = act.ReloadConfiguration },
  
  -- Toggle fullscreen
  { key = "F11", mods = "NONE", action = act.ToggleFullScreen },
}

-- ===== MOUSE BINDINGS =====
config.mouse_bindings = {
  -- Open links with CTRL+click
  {
    event = { Up = { streak = 1, button = "Left" } },
    mods = "CTRL",
    action = act.OpenLinkAtMouseCursor,
  },
  -- Paste on middle click
  {
    event = { Up = { streak = 1, button = "Middle" } },
    mods = "NONE",
    action = act.PasteFrom("PrimarySelection"),
  },
  -- Paste on right click
  {
    event = { Down = { streak = 1, button = "Right" } },
    mods = "NONE",
    action = act.PasteFrom("Clipboard"),
  },
}

-- ===== HYPERLINKS =====
config.hyperlink_rules = wezterm.default_hyperlink_rules()

-- Return the configuration
return config