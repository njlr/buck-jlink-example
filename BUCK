# Currently this doesn't work. 
# Is this a bug in Buck? 

# java_library(
#   name = 'hello', 
#   source = '10', 
#   target = '10', 
#   srcs = glob([
#     'src/module-info.java', 
#     'src/hello/**/*.java', 
#   ]), 
# )

# But here's a work-around... 

genrule(
  name = 'hello', 
  out = 'hello', 
  srcs = glob([
    'src/module-info.java', 
    'src/hello/**/*.java', 
  ]), 
  cmd = 'javac -d $OUT $SRCS', 
)

genrule(
  name = 'hello-app', 
  out = 'hello-app', 
  cmd = 'jlink --module-path $(location :hello) --add-modules hello --output $OUT --launcher launch=hello/hello.Main', 
)
