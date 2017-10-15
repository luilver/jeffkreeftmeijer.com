require 'asciidoctor'

task :generate do
  {
    '_articles/git-flow/git-flow.adoc' => '_output/git-flow/',
    '_articles/vim-number/vim-number.adoc' => '_output/vim-number/',
    '_articles/open-source-maintainability/index.adoc' => '_output/open-source-maintainability/',
  }.each do |from, to|
    {
      'amp' => 'amp.html',
      'html5' => 'index.html'
    }.each do |backend, filename|
      Asciidoctor.convert_file(
        from,
        {
          to_file: "#{to}/#{filename}",
          template_dir: "_layouts/#{backend}",
          safe: 0,
          header_footer: true,
          attributes: {
            "experimental" => '',
            "idprefix" => '',
            "idseparator" => '-',
            "tip-caption" => '💡',
            "warning-caption" => '⚠️',
            "note-caption" => 'ℹ️',
            "asset-dir-key" => "url"
          }
        }
      )
    end
  end
end
