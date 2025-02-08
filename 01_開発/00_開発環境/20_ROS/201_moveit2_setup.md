# MoveIt2 


## 
以下のWarningが出る
```
[rviz2-3] [WARN] [1692169819.789439358] [moveit_ros.planning_scene_monitor.planning_scene_monitor]: Maybe failed to update robot state, time diff: 0.106s
```
このあたりが原因？
https://github.com/ros-planning/moveit2/issues/1480  
https://github.com/ros-planning/moveit2/issues/1811

参考に、Node立ち上げ時の`parameters`に`{"use_sim_time": True}`を追加してみる。  
ただし、`launch.py`は`moveit_configs_utils`を使用しているため、陽にNode立ち上げ時のコードが無い。  
[`launches.py`](https://moveit.picknik.ai/main/api/html/launches_8py_source.html)には以下の記載がある。  
```
     move_group_params = [
         moveit_config.to_dict(),
         move_group_configuration,
     ]
  
     add_debuggable_node(
         ld,
         package="moveit_ros_move_group",
         executable="move_group",
         commands_file=str(moveit_config.package_path / "launch" / "gdb_settings.gdb"),
         output="screen",
         parameters=move_group_params,
         extra_debug_args=["--debug"],
         # Set the display variable, in case OpenGL code is used internally
         additional_env={"DISPLAY": os.environ["DISPLAY"]},
     )
```
したがって、生成した`moveit_config`に`{"use_sim_time": True}`を追加すれば良いということになる。  
が、そのやり方がよくわからん・・・  
結局launchを作成する