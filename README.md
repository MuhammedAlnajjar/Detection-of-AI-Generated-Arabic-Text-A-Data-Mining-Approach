# Detection-of-AI-Generated-Arabic-Text-A-Data-Mining-Approach
#!/usr/bin/perl
use strict;
use warnings;
use File::Path qw(make_path);
# === Project name ===
my $project_root = "Detection-of-AI-Generated-Arabic-Text-A-Data-Mining-Approach";

# === Define subdirectories ===
my @dirs = (
    "$project_root/data/raw",
    "$project_root/data/processed",
    "$project_root/data/external",
    "$project_root/notebooks",
    "$project_root/src",
    "$project_root/models",
    "$project_root/reports/figures",
    "$project_root/reports/presentations",
    "$project_root/docs"
);

# === Create directories ===
make_path(@dirs);

# === Create some example placeholder files ===
open my $fh, '>', "$project_root/requirements.txt" or die $!;
print $fh "# List of Python packages\n";
close $fh;

open $fh, '>', "$project_root/environment.yml" or die $!;
print $fh "# Conda environment specification\n";
close $fh;

open $fh, '>', "$project_root/.gitignore" or die $!;
print $fh "# Ignore data and temp files\n";
close $fh;

# === Optionally create empty Python scripts in src/ ===
my @scripts = qw(data_preparation.py modeling.py visualization.py utils.py);
foreach my $script (@scripts) {
    open my $sfh, '>', "$project_root/src/$script" or die $!;
    print $sfh "# $script\n";
    close $sfh;
}

print "Project structure created under $project_root\n";
