# Adhesive-RetnAddr-checking

Lowk shitpost but i just wanted to share my little finding so maybe someone can research it more or smth.

Ive found two functions that are responsible for verification of retnaddr:
# Code:
0x3B4870
Code:
bool __fastcall evaluate_retaddr_allow_deny_stage1(unsigned int gate_tag, void *caller_retaddr, unsigned __int64 arg3, unsigned __int64 arg4, unsigned __int8 arg5, unsigned __int64 arg6)
and if the stage 1 check fails it calls:

# Code:
0x29FF190
Code:
bool __fastcall is_retaddr_in_allowed_ranges(unsigned __int64 caller_retaddr)
if both fails it calls some heavily encrypted dispatcher (99.9% ban)

also if u hook them and for example call getNativeHandler u can see if your method is detected or not
