ユーザーの入力を受け取る
====================

方向キーの入力に合わせて移動する
--------------------
キーボードやゲームパッドの方向キーが押されているかを判定します。

![](img/Input_VirtualController_1.gif)

```cpp
#include <Lumino.h>
using namespace ln;

void Main()
{
	Engine::initialize();

	auto icon = GlyphIcon2D::create("fa-star", 64);

	Vector3 pos(100, 100, 0);

	while (Engine::update())
	{
		// ← ボタンが押されていたら
		if (Input::isPressed(InputButtons::Left))
		{
			pos.x -= 1.0;
		}

		// → ボタンが押されていたら
		if (Input::isPressed(InputButtons::Right))
		{
			pos.x += 1.0;
		}

		// ↑ ボタンが押されていたら
		if (Input::isPressed(InputButtons::Up))
		{
			pos.y -= 1.0;
		}

		// ↓ ボタンが押されていたら
		if (Input::isPressed(InputButtons::Down))
		{
			pos.y += 1.0;
		}

		// アイコンの位置を設定する
		icon->setPosition(pos);
	}
}
```





