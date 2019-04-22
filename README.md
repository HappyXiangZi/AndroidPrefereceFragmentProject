# AndroidPrefereceFragmentProject
PreferenceFragment
# 实验内容 使用 PrefereceFragment

```
package com.example.androidpreferecefragmentproject;

import android.support.v4.app.FragmentManager;
import android.support.v4.app.FragmentTransaction;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        getFragmentManager().beginTransaction().add(R.id.FrameLayout1,new PrefFragment()).commit();

    }
}

```

```
package com.example.androidpreferecefragmentproject;

import android.os.Bundle;
import android.preference.PreferenceFragment;
public class PrefFragment extends PreferenceFragment {
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        addPreferencesFromResource(R.xml.preferences);
    }
}
```

```
<?xml version="1.0" encoding="utf-8"?>
<PreferenceScreen xmlns:android="http://schemas.android.com/apk/res/android">
    <PreferenceCategory
        android:title="inline"
        android:key="inline"
        >
        <CheckBoxPreference
            android:title="@string/CheckBoxPreference"
            android:key="@string/CheckBoxPreference"
            android:summary="this is a CheckBoxPreference"/>
    </PreferenceCategory>
    <PreferenceCategory
        android:title="Dialog-based"
        android:key="Dialog-based">
        <EditTextPreference
            android:dialogTitle="EditTextPreference"
            android:key="edittext_preference"
            android:summary="一个使用了编辑文本对话框的例子"
            android:title="EditTextPreference" />

        <ListPreference
            android:dialogTitle="ListPreference"
            android:entries="@array/arrayItems"
            android:entryValues="@array/arrayValues"
            android:key="list_preferenc"
            android:summary="一个使用了列表对话框的例子"
            android:title="ListPreference" />
    </PreferenceCategory>
    <PreferenceCategory
        android:key="Launch preferences"
        android:title="Launch preferences"
        >
        <PreferenceScreen
            android:title="PreferenceScreen"
            android:summary="跳转到另一个Preference"
            >
            <CheckBoxPreference
                android:title="这是另一个Preference"
                >

            </CheckBoxPreference>
        </PreferenceScreen>
        <PreferenceScreen
            android:summary="从一个意图中启动一个activity"
            android:title="意图首选项" >
            <intent
                android:action="android.intent.action.VIEW"
                android:data="http://www.baidu.com" />
        </PreferenceScreen>

    </PreferenceCategory>

    <PreferenceCategory android:title="Preference attributes" >
        <CheckBoxPreference
            android:key="parent_checkbox_preference"
            android:summary="这是一个可见的父类"
            android:title="父类复选框首选项" />
        <!-- 子类的可见类型是由样式属性定义的 -->
        <CheckBoxPreference
            android:dependency="parent_checkbox_preference"
            android:key="child_checkbox_preference"
            android:summary="这是一个可见的子类"
            android:title="子类复选框首选项" />
    </PreferenceCategory>
</PreferenceScreen>
```

![](http://ww1.sinaimg.cn/large/8cc1690dgy1g2bgzdnyqfj209q0g80tt.jpg)

![1555920022809](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1555920022809.png)

![](http://ww1.sinaimg.cn/large/8cc1690dgy1g2bh0cka48j209q0g8752.jpg)

![](http://ww1.sinaimg.cn/large/8cc1690dgy1g2bh15nftqj20aq06fjrn.jpg)

![](http://ww1.sinaimg.cn/large/8cc1690dgy1g2bh21i4ohj209q0g80uv.jpg)

