genrule (
	name = "_generated",
	outs = ["generated.srcjar"],
	cmd = """
		set -x
		OUTDIR=$(@D)/generated
		rm -rf $$OUTDIR
		mkdir $$OUTDIR
		echo "public class Generated { public String getMessage() { return \\"Hello generated!\\"; } }" > $$OUTDIR/Generated.java
		jar cf $@ -C $$OUTDIR .
	"""
)

java_binary (
	name = "main",
	srcs = ["static/Static.java", "_generated"],
	main_class = "Static",
)