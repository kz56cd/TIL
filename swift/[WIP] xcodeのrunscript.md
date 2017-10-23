# [WIP] xcodeのrunscript

- build時に実行されるshell script

### swiftGen

if which swiftgen >/dev/null; then
swiftgen storyboards --template swift3 "$PROJECT_DIR/OfficeReception" --output "$PROJECT_DIR/OfficeReception/StoryboardScene.swift"
swiftgen xcassets --template swift3 "$PROJECT_DIR/OfficeReception/Assets.xcassets" --output "$PROJECT_DIR/OfficeReception/Asset.swift"
swiftgen colors --template swift3 "$PROJECT_DIR/OfficeReception/colors.txt" --output "$PROJECT_DIR/OfficeReception/ColorName.swift"
swiftgen fonts --template swift3 "$PROJECT_DIR/OfficeReception/Fonts" --output "$PROJECT_DIR/OfficeReception/FontFamily.swift"
else
echo "warning: SwiftGen not installed, download it from https://github.com/AliSoftware/SwiftGen"
fi

### swiftlint

if which swiftlint >/dev/null; then
swiftlint
else
echo "warning: SwiftLint not installed, download from https://github.com/realm/SwiftLint"
fi

### carthage

- https://qiita.com/yutat93/items/97fe9bc2bf2e97da7ec1