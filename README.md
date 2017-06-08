# aredis
a clean redis C++ client

```cpp
redis_conn rc;
if (rc.connect("127.0.0.1"/*host*/, 6379/*port*/, nullptr/*password*/, 1/*db*/))
{
  redis_command cmd;
  cmd.cmd("set", "test", 123);
  rc.command(cmd);
  resp_result res;
  if (rc.reply(res))
  {
    std::cout << res.dump();
  }
  cmd.cmd("get", "test");
  rc.command(cmd);
  if (rc.reply(res))
  {
    std::cout << res.dump();
  }
}

```
